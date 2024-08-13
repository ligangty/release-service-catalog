# publish-to-mrrc

Tekton task that publishs the maven artifacts to MRRC(maven.repository.redhat.com) service. MRRC is used to host maven artifacts of Red Hat Middleware products.
This task will work with [collect-mrrc-task](../collect-mrrc-params/README.md) together to do the MRRC publishment work. It accepts the `mrrc.env` file from the [collect-mrrc-task](../collect-mrrc-params/README.md) and use the variables in it as parameters for the MRRC publishing task. It also uses `cosignPubKeyConfig` as public key to do the maven zip signature and attestation check.

## Parameters

| Name               | Description                                                                                                                                     | Optional | Default value |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------- | -------- | ------------- |
| mrrcParamFilePath  | Path of the mrrc.env file which contains the MRRC parameters as environment viariables                                                          | No       | -             |
| charonAWSSecret    | The secret which contains the aws credential settings for the charon usage                                                                      | No       | -             |
