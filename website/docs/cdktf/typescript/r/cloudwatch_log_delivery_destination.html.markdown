---
subcategory: "CloudWatch Logs"
layout: "aws"
page_title: "AWS: aws_cloudwatch_log_delivery_destination"
description: |-
  Terraform resource for managing an AWS CloudWatch Logs Delivery Destination.
---


<!-- Please do not edit this file, it is generated. -->
# Resource: aws_cloudwatch_log_delivery_destination

Terraform resource for managing an AWS CloudWatch Logs Delivery Destination.

## Example Usage

### Basic Usage

```typescript
// DO NOT EDIT. Code generated by 'cdktf convert' - Please report bugs at https://cdk.tf/bug
import { Construct } from "constructs";
import { Token, TerraformStack } from "cdktf";
/*
 * Provider bindings are generated by running `cdktf get`.
 * See https://cdk.tf/provider-generation for more details.
 */
import { CloudwatchLogDeliveryDestination } from "./.gen/providers/aws/cloudwatch-log-delivery-destination";
class MyConvertedCode extends TerraformStack {
  constructor(scope: Construct, name: string) {
    super(scope, name);
    new CloudwatchLogDeliveryDestination(this, "example", {
      deliveryDestinationConfiguration: [
        {
          destinationResourceArn: Token.asString(
            awsCloudwatchLogGroupExample.arn
          ),
        },
      ],
      name: "example",
    });
  }
}

```

## Argument Reference

This resource supports the following arguments:

* `deliveryDestinationConfiguration` - (Required) The AWS resource that will receive the logs.
    * `destinationResourceArn` - (Required) The ARN of the AWS destination that this delivery destination represents.
* `name` - (Required) The name for this delivery destination.
* `outputFormat` - (Optional) The format of the logs that are sent to this delivery destination. Valid values: `json`, `plain`, `w3c`, `raw`, `parquet`.
* `tags` - (Optional) A map of tags to assign to the resource. If configured with a provider [`defaultTags` configuration block](https://registry.terraform.io/providers/hashicorp/aws/latest/docs#default_tags-configuration-block) present, tags with matching keys will overwrite those defined at the provider-level.

## Attribute Reference

This resource exports the following attributes in addition to the arguments above:

* `arn` - The Amazon Resource Name (ARN) of the delivery destination.
* `deliveryDestinationType` - Whether this delivery destination is CloudWatch Logs, Amazon S3, or Firehose.
* `tagsAll` - A map of tags assigned to the resource, including those inherited from the provider [`defaultTags` configuration block](https://registry.terraform.io/providers/hashicorp/aws/latest/docs#default_tags-configuration-block).

## Import

In Terraform v1.5.0 and later, use an [`import` block](https://developer.hashicorp.com/terraform/language/import) to import CloudWatch Logs Delivery Destination using the `name`. For example:

```typescript
// DO NOT EDIT. Code generated by 'cdktf convert' - Please report bugs at https://cdk.tf/bug
import { Construct } from "constructs";
import { TerraformStack } from "cdktf";
/*
 * Provider bindings are generated by running `cdktf get`.
 * See https://cdk.tf/provider-generation for more details.
 */
import { CloudwatchLogDeliveryDestination } from "./.gen/providers/aws/cloudwatch-log-delivery-destination";
class MyConvertedCode extends TerraformStack {
  constructor(scope: Construct, name: string) {
    super(scope, name);
    CloudwatchLogDeliveryDestination.generateConfigForImport(
      this,
      "example",
      "example"
    );
  }
}

```

Using `terraform import`, import CloudWatch Logs Delivery Destination using the `name`. For example:

```console
% terraform import aws_cloudwatch_log_delivery_destination.example example
```

<!-- cache-key: cdktf-0.20.8 input-56de156b90cc249064b0e8d1082ac667c0ce72fb3110e4432de4bc29e2acbdfe -->