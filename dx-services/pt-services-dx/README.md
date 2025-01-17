# Collection Service (collection-service)

 generates Payment for bills generated by billing service.

### DB UML Diagram

NA

### Service Dependencies

 - User Service (egov-user)
 - Finance Master Service (egf-master)
 - Common Master Service (egov-common-masters)
 - Instrument Service (egf-instrument)
 - Billing Service (billing-service)
 - ID Generation Service (egov-idgen)
 - MDM Service (egov-mdms-service)
 - Apportion Service (egov-apportion-service)

### Swagger API Contract

  https://editor.swagger.io/?url=https://raw.githubusercontent.com/upyog/UPYOG/master/business-services/Docs/collection-services/V-2-0.yml#!/

## Service Details

collects payment for bills from CITIZEN and EMPLOYEE for the bills generated by revenue services using different modes of services of online and offline (employee counter).

### API Details

  - payment/_create - the payment set of API's collects payments based on bill Id. it validates whether the bill for which payment is being made is either a valid bill or not. incase of invaid or expired bills error will be thrown.
  - payment/_workflow - The update API for payment where payment can be remitted/deposited or cancelled in case of invalid payments.
  
### Kafka Consumers

-kafka.topics.payment.create.name=
-kafka.topics.payment.cancel.name=
-kafka.topics.payment.update.name=

Kafka consumer listen to payment topic to update demand whenever payment is made against the bills.

### Kafka Producers

-kafka.topics.payment.create.name=
-kafka.topics.payment.cancel.name=
-kafka.topics.payment.update.name=

