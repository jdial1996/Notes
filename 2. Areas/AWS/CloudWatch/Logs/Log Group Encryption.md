**At Rest Encryption**
- Cloudwatch Log group data is always encrypted at rest using default AES256 encryption, however you can use CMKs with KMS for at rest encryption instead
- Encryption is enabled at the log group level 
- Once a KMS key is associated with a log group, all newly ingested data is encrypted.  The data is stored in an encrypted format for the duration of its retention period. 
- If you disassociate a KMS from a log group, from that point log data in the log group is encrypted using default AES256 encryption.
	- All previously encrypted data remains encrypted with the disassociated KMS key and is retainable as long as the KMS key is not disabled.  

**Set up At Rest Encryption** **(CMK)**
1. Create KMS Key
2. Set permissions on KMS key to allow the Cloudwatch logs service principal and the caller role permission to use the key 
	1. ***By default all kms keys are private***
	2. ***Use KMS encryption contexts to limit KMS keys to a log group.***
		1. KMS encryption contexts act like IAM conditions for KMS key policies
3. Associate the KMS key with a log group

**In transit Encryption**
- Cloudwatch logs uses end to end encryption of data in transit. 
- 