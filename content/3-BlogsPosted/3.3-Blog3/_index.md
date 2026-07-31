---
title: "Blog 3"
date: 2026-07-29
weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---

# UNDERSTANDING AWS RESOURCE EXPLORER – SEARCHING AWS RESOURCES MORE EASILY

While learning AWS, I realized that as the number of services and resources increases, managing them becomes more difficult. There are times when I remember creating a Lambda Function or an EC2 Instance but cannot remember exactly which Region it is in or what its full name is.

After researching AWS documentation, I learned about AWS Resource Explorer. This is a service that allows you to search for resources on AWS through a unified interface, instead of having to open each service to find them. Resource Explorer can index resources in the account and supports searching by name, resource type, or Region.

## What can AWS Resource Explorer do?

After reading the documentation and trying it out, I found that Resource Explorer supports quite a few practical use cases such as:

- Quickly finding an EC2 Instance, S3 Bucket, Lambda Function, or DynamoDB Table.
- Searching for resources by Region.
- Searching for resources by name or ARN.
- Checking whether a resource has been deleted or still exists.
- Supporting management when an account has multiple Regions or multiple projects.

{{% notice note %}}
This service is especially useful when you start having multiple environments like Development, Testing, and Production.
{{% /notice %}}

## Trying out AWS Resource Explorer

To understand it better, I tried configuring it according to AWS's instructions.

**Step 1:** Access the AWS Console and search for AWS Resource Explorer.

**Step 2:** Select Create Index.

The Index helps AWS collect information about the resources in your account. It usually takes just a few minutes to complete.

**Step 3:** Create a Default View.

The View determines the scope of resources that can be searched. It can be limited by Region or allow searching across multiple Regions.

**Step 4:** Start searching.

For example, I enter:

```text
resourcetype:ec2:instance
```

to display all EC2 Instances.

Or search by name:

```text
movie-api
```

AWS will return resources with matching names or metadata.

## Advantages

After trying it out, I noticed Resource Explorer has several advantages:

- No need to open each service to find a resource.
- Supports searching across multiple Regions.
- Simple and easy-to-use interface.
- Can search using various different conditions.
- Suitable as the number of resources increases.

{{% notice tip %}}
In my opinion, if you are just learning AWS, you might not clearly feel the benefits yet. But when deploying multiple projects or managing a shared AWS account for multiple teams, searching for resources will be much faster.
{{% /notice %}}

## Some points to note

Besides the advantages above, I also found a few things to keep in mind.

First of all, Resource Explorer needs to have an Index created before use. If there is no Index, you cannot search for resources. Additionally, search results depend on the user's IAM permissions. If an IAM User or IAM Role does not have permission to view a certain resource, Resource Explorer will not display that resource either.

{{% notice note %}}
This is a tool to support searching and managing resources; it does not replace management or monitoring services like AWS Config or CloudWatch.
{{% /notice %}}

## When to use it?

In my opinion, Resource Explorer is suitable when:

- Managing multiple AWS services within the same account.
- Working with multiple Regions.
- Wanting to quickly find a resource without remembering its exact location.
- Checking if resources still exist before cleaning up or optimizing costs.

## Conclusion
After exploring, I found that AWS Resource Explorer is a fairly simple service but very useful in the process of managing resources on AWS. Instead of having to open each service and search manually, just a single interface is enough to look up most of the resources in the account.

I think this is a service worth trying, especially when the number of resources starts to increase or when working on projects with multiple environments and Regions.

## References
1. [AWS Documentation – AWS Resource Explorer](https://docs.aws.amazon.com/resource-explorer/latest/userguide/welcome.html)
2. [Getting Started with AWS Resource Explorer](https://docs.aws.amazon.com/resource-explorer/latest/userguide/getting-started.html)
3. [Search syntax for AWS Resource Explorer](https://docs.aws.amazon.com/resource-explorer/latest/userguide/using-search-query.html)