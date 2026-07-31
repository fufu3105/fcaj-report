---
title: "Blog 1"
date: 2026-07-29
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# EXPLORING AWS RESOURCE EXPLORER – FIND AWS RESOURCES ACROSS MULTIPLE REGIONS FROM A SINGLE PLACE

While using the AWS Console, I noticed a fairly simple yet time-consuming issue: not remembering which Region a resource was created in.

For example, I know the account has an EC2 instance or a DynamoDB table, but when I open the service, I don't see it. After checking for a while, I discover that the resource was created in a different Region.

AWS has a service to help solve this problem: **AWS Resource Explorer**. This service allows searching for resources in an AWS account based on name, ID, Region, resource type, and tags. The usage is quite similar to a search engine dedicated to AWS resources.

## What is AWS Resource Explorer used for?

In an AWS account, resources can be scattered across multiple places, such as:

- EC2 instance in Singapore.
- DynamoDB table in Tokyo.
- Lambda function in North Virginia.
- S3 bucket with global scope.
- Some experimental resources created previously but not yet deleted.

Instead of switching between each Region and opening each service one by one to check, Resource Explorer allows searching for these resources from a unified interface.

{{% notice note %}}
Resource Explorer maintains indexes containing information about resources in each Region. When configuring a Region as an aggregator index, users can search for resources from multiple Regions in one place.
{{% /notice %}}

## Practical Steps

In this practical exercise, we will try to find EC2 and S3 resources, as well as resources that have not been tagged.

**Step 1:** Access AWS Resource Explorer.

Log in to the AWS Management Console and search for: AWS Resource Explorer

Then select Resource search.

AWS currently allows users with appropriate permissions to start searching right away when accessing the service. With the `AWSResourceExplorerReadOnlyAccess` policy, users can receive initial search results. To have a complete inventory and automatically create necessary components, the account needs additional `iam:CreateServiceLinkedRole` permissions, which are included in the `AWSResourceExplorerFullAccess` policy.

**Step 2:** Try finding all EC2 resources.

In the search box, enter:

```text
service:ec2
```

This query returns resources managed by Amazon EC2 that Resource Explorer has indexed.
If you only want to find EC2 instances, you can use a more specific query:

```text
resourcetype:ec2:instance
```

Resource Explorer supports filters such as `service`, `resourcetype`, `region`, `tag`, and various other metadata types.

**Step 3:** Find resources in a Region.

To find resources in the Singapore Region, enter:

```text
region:ap-southeast-1
```

You can combine multiple conditions:

```text
service:ec2 region:ap-southeast-1
```

The above query only searches for resources belonging to EC2 in the Singapore Region.

{{% notice tip %}}
When using multiple filters, Resource Explorer combines them to narrow down search results. This is quite convenient when an account has many different types of resources.
{{% /notice %}}

**Step 4:** Find resources by tag.

Suppose production resources are tagged:

```text
Environment=Production
```

You can search using the query:

```text
tag:Environment=Production
```

Or combine it with the service type:

```text
service:ec2 tag:Environment=Production
```

To search by tag, the view being used must be configured to include the `tags` attribute. The default view created during full setup typically supports this search.

**Step 5:** Find untagged resources
One query I found quite useful is:

```text
tag:none
```

This query returns resources that do not have user-created tags.

In practice, finding untagged resources helps review resources that have not been classified by project, environment, or owner. This can also be the first step before reviewing costs or cleaning up test resources.

You can limit the results to a specific Region:

```text
tag:none region:ap-southeast-1
```

**Step 6:** Enable multi-Region search

If cross-Region search is not yet enabled for the account, go to: AWS Resource Explorer → Settings

Select **Complete setup and enable cross-Region search**. Next:

1. Choose a Region as the aggregator index, such as Singapore.
2. Select **Enable cross-Region search in all Regions**.
3. Confirm the setup.
4. Monitor the indexing status.
5. Once completed, return to Resource search and select the view belonging to the aggregator Region.

AWS will create indexes in the selected regions, convert the main region's index into an aggregator index, and create a default view to search for resources across those regions.

{{% notice note %}}
Note that indexing does not always complete immediately. According to AWS documentation, tagged resources usually appear after a few minutes, while untagged resources may take longer. Initial synchronization to the aggregator index may also have some latency.
{{% /notice %}}

## What I find useful

The most useful aspect of Resource Explorer is not having to remember exactly which Region a resource is located in.

This service also supports searching by multiple types of metadata. For example, instead of just searching by resource name, users can search by service, resource type, Region, or tag.

Resource Explorer is also integrated with the Unified Search bar on the AWS Management Console. Therefore, in some cases, you can search for resources directly in the top search bar of the Console without opening Resource Explorer separately.

Another point is that Resource Explorer supports using views to control the scope of resources that individual users are allowed to find. For example, a view can be set to only display resources tagged with `Environment=Production`, and then access to that view can be granted only to the appropriate operations team.

## Some limitations to keep in mind

Resource Explorer is a resource search and discovery tool, not a full resource management tool. After finding an EC2 instance or DynamoDB table, users usually still need to open the management page of the respective service to change configurations.

Search results also depend on IAM permissions, views, and indexing status. Therefore, the fact that a resource does not appear does not necessarily mean that the resource does not exist.

With basic read-only permissions, users may only receive partial results. If you want a complete inventory or want to search across multiple regions, additional setup and appropriate permissions are required.

Additionally, when using free-form keywords, the Search operation has a limit on the number of results returned. If an account has a large number of resources, you should use additional filters such as Region, service, or resource type to narrow down the results.

## Cost

According to AWS pricing, Resource Explorer is provided without additional usage fees and has no initial setup fees.

However, some features displayed in Resource Explorer may depend on other services such as AWS Config. Related services may still charge separately. Some List or Describe APIs of services called may also incur charges if those services apply pricing to these APIs.

## Conclusion

After trying AWS Resource Explorer, I found it to be a fairly simple yet useful service, especially when an account has resources spread across multiple regions.

This service does not directly optimize costs or system security, but it helps users get a clearer picture of existing resources. As a result, checking test resources, finding missing tags, or locating a resource becomes faster.

For learning accounts, Resource Explorer can also help check whether you accidentally left resources behind in another region after completing a lab.

Has anyone ever encountered the situation where they couldn't find a resource just because they selected the wrong Region? I'd love to hear more real-world use cases of Resource Explorer.

## References

1. [AWS Resource Explorer User Guide:](https://docs.aws.amazon.com/.../userguide/welcome.html)

2. [Getting started with Resource Explorer:](https://docs.aws.amazon.com/resource-explorer/latest/userguide/getting-started.html)

3. [Searching for resources:](https://docs.aws.amazon.com/resource-explorer/latest/userguide/using-search.html)

4. [Resource Explorer query syntax:](https://docs.aws.amazon.com/resource-explorer/latest/userguide/using-search-query-syntax.html)

5. [Search query examples:](https://docs.aws.amazon.com/resource-explorer/latest/userguide/using-search-query-examples.html)

6. [Setting up cross-Region search:](https://docs.aws.amazon.com/resource-explorer/latest/userguide/getting-started-setting-up.html)

7. [AWS Resource Explorer Pricing:](https://aws.amazon.com/resourceexplorer/pricing/)