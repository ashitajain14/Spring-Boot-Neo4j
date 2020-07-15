# Neo4j 

# Creating nodes and realationships

CREATE(Project:Project{project_name:'UIP'})
CREATE(Inventory:division{sub_project_name:'Inventory_team'})
CREATE (Inventory)-[:IS_PROJECT]->(Project)
CREATE(Procurement:division{sub_project_name:'Procurement_team'})
CREATE (Procurement)-[:IS_PROJECT]->(Project)

CREATE(Functionality1:functionality{func_name:'E-invoice'})
CREATE (Functionality1)-[:HAS_FUNCTIONALITY]->(Inventory)
CREATE(Functionality2:functionality{func_name:'CostRecovery'})
CREATE (Functionality2)-[:HAS_FUNCTIONALITY]->(Inventory)

CREATE(Functionality3:functionality{func_name:'Invoice'})
CREATE (Functionality3)-[:HAS_FUNCTIONALITY]->(Procurement)
CREATE(Functionality4:functionality{func_name:'Cost'})
CREATE (Functionality4)-[:HAS_FUNCTIONALITY]->(Procurement)

CREATE(Service1:service{service_name:'xxiap034-novora-e-invoice-loader-service', project_id:48652, code_base:'https://gitlab.dell.com/globalops/BPM/global-inventory/prism-inventory/edi-810-invoice/xxiap034-novora-e-invoice-loader-service'})
CREATE (Service1)-[:HAS_SERVICE]->(Functionality1)
CREATE(Service2:service{service_name:'xxiap034-e-invoice-status-check-service', project_id:48654, code_base:'https://gitlab.dell.com/globalops/BPM/global-inventory/prism-inventory/edi-810-invoice/e-invoice-status-check-service'})
CREATE (Service2)-[:HAS_SERVICE]->(Functionality1)
CREATE(Service3:service{service_name:'XXIAP012-Invoice-Outbound-payment-update-service', project_id:31879 ,code_base:'https://gitlab.dell.com/globalops/BPM/global-inventory/prism-inventory/edi-810-invoice/payment-updation-services', Kerberos: 'Yes', Common_Logger_Verified: 'Yes'})
CREATE (Service3)-[:HAS_SERVICE]->(Functionality2)
CREATE(Service4:service{service_name:'CostRecovery-Trigger-Service', project_id:49145, code_base:'https://gitlab.dell.com/globalops/BPM/global-inventory/prism-inventory/edi-810-invoice/cost-recovery-trigger-service', Kerberos: 'Yes'})
CREATE (Service4)-[:HAS_SERVICE]->(Functionality2)
CREATE(Service9:service{service_name:'Novora-e-invoice-loader-service', project_id:46969, code_base:'https://gitlab.dell.com/globalops/BPM/global-inventory/prism-inventory/edi-810-invoice'})
CREATE (Service9)-[:HAS_SERVICE]->(Functionality1)
CREATE(Service10:service{service_name:'glovia-item-data-service', project_id:17691, code_base:'https://gitlab.dell.com/globalops/BPM/global-inventory/prism-inventory/item-conversion/item-conversion/glovia-item-data-service.git'})
CREATE (Service10)-[:HAS_SERVICE]->(Functionality1)
CREATE(Service11:service{service_name:'item-storage-service', project_id:17649, code_base:'https://gitlab.dell.com/globalops/BPM/global-inventory/prism-inventory/item-conversion/readitemfromkafkatomongo.git'})
CREATE (Service11)-[:HAS_SERVICE]->(Functionality1)
CREATE(Service12:service{service_name:'inter-org-api(Direct Org API)', project_id:48871, code_base:'https://gitlab.dell.com/globalops/BPM/global-inventory/prism-inventory/star-item/inter-org-api.git'})
CREATE (Service12)-[:HAS_SERVICE]->(Functionality1)
CREATE(Service13:service{service_name:'warehouse-transfers-listener-service', project_id:28042, code_base:'https://gitlab.dell.com/globalops/BPM/global-inventory/prism-inventory/warehouse-transfers/warehouse-consumer-service.git'})
CREATE (Service13)-[:HAS_SERVICE]->(Functionality1)
CREATE(Service14:service{service_name:'wh-ebs-glovia-transactions-service', project_id:34092, code_base:'https://gitlab.dell.com/globalops/BPM/global-inventory/prism-inventory/warehouse-transfers/warehouse-service.git'})
CREATE (Service14)-[:HAS_SERVICE]->(Functionality1)
CREATE(Service15:service{service_name:'git-glovia-receipt-api( Glovia RCPT API)', project_id:51552, code_base:'https://gitlab.dell.com/globalops/BPM/global-inventory/prism-inventory/global-transfer-tool/git-glovia-receipt-api.git'})
CREATE (Service15)-[:HAS_SERVICE]->(Functionality1)

CREATE(Service16:service{service_name:'inventory-transaction-message-service', project_id:27403, code_base:'https://gitlab.dell.com/globalops/BPM/global-inventory/prism-inventory/inventory-transactions/inventory-transaction-message-service.git'})
CREATE (Service16)-[:HAS_SERVICE]->(Functionality1)

CREATE(Service17:service{service_name:'service-tag-star-item-map service', project_id:27325, code_base:'https://gitlab.dell.com/globalops/BPM/global-inventory/prism-inventory/star-item/svc-tag-star-item-map-api.git'})
CREATE (Service17)-[:HAS_SERVICE]->(Functionality1)

CREATE(Service18:service{service_name:'asn-data-api', project_id:29370, code_base:'https://gitlab.dell.com/globalops/BPM/global-inventory/prism-inventory/star-item/asn-data-api.git'})
CREATE (Service18)-[:HAS_SERVICE]->(Functionality1)

CREATE(Service19:service{service_name:'obasn-inter-org-transfer-service', project_id:49687, code_base:'https://gitlab.dell.com/globalops/BPM/global-inventory/prism-inventory/star-item/obasn-inter-org-transfer-service.git'})
CREATE (Service19)-[:HAS_SERVICE]->(Functionality1)

CREATE(Service20:service{service_name:'obasn-router-service', project_id:48261, code_base:'https://gitlab.dell.com/globalops/BPM/global-inventory/prism-inventory/star-item/obasn-router-service.git'})
CREATE (Service20)-[:HAS_SERVICE]->(Functionality1)

CREATE(Service21:service{service_name:'ebs-star-item-api', project_id:26238, code_base:'https://gitlab.dell.com/globalops/BPM/global-inventory/prism-inventory/star-item/ebs-star-item-api.git'})
CREATE (Service21)-[:HAS_SERVICE]->(Functionality1)

CREATE(Owner1:owner{owner_name:'Rati_Rai@Dell.com'})
CREATE (Owner1)-[:OWNS]->(Service4)

CREATE(Service5:service{service_name:'xxiap007-service', project_id:99652, code_base:'https://gitlab.dell.com/BPM/global/prism-inventory/edi-810-invoice/xxiap034-novora-e-invoice-loader-service'})
CREATE (Service5)-[:HAS_SERVICE]->(Functionality3)
CREATE(Service6:service{service_name:'xxiap008-e-status-service', project_id:48664, code_base:'https://gitlab.dell.com/globalops/prism-inventory/edi-810-invoice/e-invoice-status-check-service'})
CREATE (Service6)-[:HAS_SERVICE]->(Functionality3)
CREATE(Service7:service{service_name:'XXIAP009-update-service', project_id:31879 ,code_base:'https://gitlab.dell.com/payment-updation-services', Kerberos: 'Yes', Common_Logger_Verified: 'Yes'})
CREATE (Service7)-[:HAS_SERVICE]->(Functionality4)
CREATE(Service8:service{service_name:'CostRecovery-Trigger-Service', project_id:41115, code_base:'https://gitlab.dell.com/prism-procurement/edi-810-invoice', Kerberos: 'Yes'})
CREATE (Service8)-[:HAS_SERVICE]->(Functionality4)

CREATE(Service22:service{service_name:'hub-lite-ui', project_id:00001, code_base:'https://gitlab.dell.com/globalops/BPM/Procurement/direct/prism-procurement/hub-lite-portal/hub-lite-ui'})
CREATE (Service22)-[:HAS_SERVICE]->(Functionality3)

CREATE(Service23:service{service_name:'procurement-dashboard-ui', project_id:00002, code_base:'https://gitlab.dell.com/globalops/BPM/Procurement/direct/prism-procurement/procurement-dashboard-portal/procurement-dashboard-ui'})
CREATE (Service23)-[:HAS_SERVICE]->(Functionality3)

CREATE(Service24:service{service_name:'procurement-dashboard', project_id:00003 ,code_base:'https://gitlab.dell.com/globalops/BPM/Procurement/direct/prism-procurement/procurement-dashboard-portal/procurement-dashboard-services'})
CREATE (Service24)-[:HAS_SERVICE]->(Functionality4)

CREATE(Service25:service{service_name:'hub-lite-portal-services-xxihc031', project_id:00004, code_base:'https://gitlab.dell.com/globalops/BPM/Procurement/direct/prism-procurement/hub-lite-portal/digital-hub-services/hub-lite-portal-services-xxihc031'})
CREATE (Service25)-[:HAS_SERVICE]->(Functionality4)

CREATE(Service26:service{service_name:'hub-lite-reports-service-xxihc031', project_id:00005, code_base:'https://gitlab.dell.com/globalops/BPM/Procurement/direct/prism-procurement/hub-lite-portal/digital-hub-services/hub-lite-reports-service-xxihc031'})
CREATE (Service26)-[:HAS_SERVICE]->(Functionality3)

CREATE(Service27:service{service_name:'hub-lite-vendor-selection-service-xxihc031', project_id:00006, code_base:'https://gitlab.dell.com/globalops/BPM/Procurement/direct/prism-procurement/hub-lite-portal/digital-hub-services/hub-lite-vendor-selection-service-xxihc031'})
CREATE (Service27)-[:HAS_SERVICE]->(Functionality3)

CREATE(Service28:service{service_name:'inventory-snapshot-service-xxihc031', project_id:00007 ,code_base:'https://gitlab.dell.com/globalops/BPM/Procurement/direct/prism-procurement/hub-lite-portal/digital-hub-services/inventory-snapshot-service-xxihc031'})
CREATE (Service28)-[:HAS_SERVICE]->(Functionality4)

CREATE(Service31:service{service_name:'material-request-ack-nack-service-xxihc031', project_id:00010, code_base:'https://gitlab.dell.com/globalops/BPM/Procurement/direct/prism-procurement/hub-lite-portal/digital-hub-services/material-request-ack-nack-service-xxihc031'})
CREATE (Service31)-[:HAS_SERVICE]->(Functionality3)

CREATE(Service32:service{service_name:'sup-email-notification-service-xxipo003', project_id:00011 ,code_base:'https://gitlab.dell.com/globalops/BPM/Procurement/direct/prism-procurement/sup-email-notification-service'})
CREATE (Service32)-[:HAS_SERVICE]->(Functionality4)

CREATE(Service33:service{service_name:'spring-cloud-gateway-procurement', project_id:00012, code_base:'https://gitlab.dell.com/globalops/BPM/Procurement/direct/prism-procurement/spring-cloud-gateway-procurement'})
CREATE (Service33)-[:HAS_SERVICE]->(Functionality4)

CREATE(Service34:service{service_name:'purchase-order-services', project_id:00013, code_base:'https://gitlab.dell.com/globalops/BPM/Procurement/direct/prism-procurement/purchase-order-services'})
CREATE (Service34)-[:HAS_SERVICE]->(Functionality3)

CREATE(Service35:service{service_name:'po-approval-services', project_id:00014, code_base:'https://gitlab.dell.com/globalops/BPM/Procurement/direct/prism-procurement/po-approval-services'})
CREATE (Service35)-[:HAS_SERVICE]->(Functionality3)

CREATE(Service36:service{service_name:'po-edi-service', project_id:00015 ,code_base:'https://gitlab.dell.com/globalops/BPM/Procurement/direct/prism-procurement/po-edi-service'})
CREATE (Service36)-[:HAS_SERVICE]->(Functionality4)

CREATE(Service37:service{service_name:'Supplier interface', project_id:00016, code_base:'https://gitlab.dell.com/globalops/BPM/Procurement/direct/prism-procurement/supplier-consumer-services'})
CREATE (Service37)-[:HAS_SERVICE]->(Functionality4)

CREATE(Service38:service{service_name:'Digital hub PO ackNack servive', project_id:00014, code_base:'https://gitlab.dell.com/globalops/BPM/Procurement/direct/prism-procurement/hub-lite-portal/digital-hub-services/dh-po-receipt-acknack-epod-service-xxihc031'})
CREATE (Service38)-[:HAS_SERVICE]->(Functionality3)

CREATE(Service39:service{service_name:'Penny price report', project_id:00015 ,code_base:'https://gitlab.dell.com/globalops/BPM/Procurement/direct/prism-procurement/penny-po-price-rpt-service'})
CREATE (Service39)-[:HAS_SERVICE]->(Functionality4)

CREATE(Service40:service{service_name:'Mem sql Scheduler service', project_id:00016, code_base:'https://gitlab.dell.com/globalops/BPM/Procurement/dire'})
CREATE (Service40)-[:HAS_SERVICE]->(Functionality4)

CREATE(Owner2:owner{owner_name:'Bati_Rai@Dell.com'})
CREATE (Owner2)-[:OWNS]->(Service8)

CREATE(Mongo1:mongo_db{db_name:'MONGO'})
CREATE (Mongo1)-[:HAS_MONGO_DB]->(Service1)
CREATE(Mongo2:mongo_db{db_name:'MONGO'})
CREATE (Mongo2)-[:HAS_MONGO_DB]->(Service2)
CREATE(xxiap034_EInvoice_Logger:collection{collection_name:'xxiap034_EInvoice_Logger'})
CREATE (xxiap034_EInvoice_Logger)-[:HAS_COLLECTION]->(Mongo1)
CREATE (xxiap034_EInvoice_Logger)-[:HAS_COLLECTION]->(Mongo2)

CREATE(Mongo3:mongo_db{db_name:'MONGO'})
CREATE (Mongo3)-[:HAS_MONGO_DB]->(Service3)
CREATE(Mongo4:mongo_db{db_name:'MONGO'})
CREATE (Mongo4)-[:HAS_MONGO_DB]->(Service4)
CREATE(XXIAP012_INV_APINVOICENACK:collection{collection_name:'XXIAP012_INV_APINVOICENACK'})
CREATE (XXIAP012_INV_APINVOICENACK)-[:HAS_COLLECTION]->(Mongo3)
CREATE(COST_RECOVERY_TRIGGER_LOGGER:collection{collection_name:'COST_RECOVERY_TRIGGER_LOGGER'})
CREATE (COST_RECOVERY_TRIGGER_LOGGER)-[:HAS_COLLECTION]->(Mongo4)

CREATE(Mongo5:mongo_db{db_name:'MONGO'})
CREATE (Mongo5)-[:HAS_MONGO_DB]->(Service5)
CREATE(xxiap008_Logger:collection{collection_name:'xxiap008_Logger'})
CREATE (xxiap008_Logger)-[:HAS_COLLECTION]->(Mongo5)

CREATE(Oracle1:oracle_db{db_name:'ORACLE'})
CREATE (Oracle1)-[:HAS_ORACLE_DB]->(Service1)
CREATE(Oracle2:oracle_db{db_name:'ORACLE'})
CREATE (Oracle2)-[:HAS_ORACLE_DB]->(Service2)

CREATE(Oracle3:oracle_db{db_name:'ORACLE'})
CREATE (Oracle3)-[:HAS_ORACLE_DB]->(Service5)
CREATE(Oracle4:oracle_db{db_name:'ORACLE'})
CREATE (Oracle4)-[:HAS_ORACLE_DB]->(Service6)

CREATE (Table1:Oracletable{Table_name:'TABLE', Sequence: 'Sequence for the Oracle table1'})
CREATE (Table1)-[:FOR_ORACLE_DB_Table]->(Oracle3)
CREATE (Table1)-[:FOR_ORACLE_DB_Table]->(Oracle4)
CREATE (Table2:Oracletable{Table_name:'TABLE', Sequence: 'Sequence for the Oracle table2'})
CREATE (Table2)-[:FOR_ORACLE_DB_Table]->(Oracle4)

CREATE(Oracle5:oracle_db{db_name:'ORACLE'})
CREATE (Oracle5)-[:HAS_ORACLE_DB]->(Service7)

CREATE (Procedure1:Procedure{Procedure_name:'PROCEDURE'})
CREATE (Procedure1)-[:FOR_ORACLE_DB]->(Oracle4)
CREATE (Procedure1)-[:FOR_ORACLE_DB]->(Oracle5)

CREATE(Kafka1:Kafka{name:'KAFKA', Kafka_topic_name: 'GOBIG.ACKNACK.FINGW.APINVPAY.PRISM.P2.R3', produce_or_consume: 'Both'})
CREATE (Kafka1)-[:HAS_KAFKA]->(Service3)

CREATE(Kafka_group1:Kafka_group{name:'PRISMEPCCOST', group: 'consumer'})
CREATE (Kafka_group1)-[:HAS_KAFKA_GROUP]->(Kafka1)

CREATE(Kafka_group2:Kafka_group{name:'PRISMEPCCOST', group: 'producer'})
CREATE (Kafka_group2)-[:HAS_KAFKA_GROUP]->(Kafka1)

CREATE(Kafka2:Kafka{name:'KAFKA', Kafka_topic_name: 'GOBIG.PRISM.COSTRECOVERYRELIEF.P3.R3', produce_or_consume: 'Consumer'})
CREATE (Kafka2)-[:HAS_KAFKA]->(Service4)

CREATE(Kafka_group3:Kafka_group{name:'CRRELIEF', group: 'consumer'})
CREATE (Kafka_group3)-[:HAS_KAFKA_GROUP]->(Kafka2)

CREATE(Rabbit1:rabbit{que_type:'RABBIT'})
CREATE(ED810_INVOICE_DATA_RES:queue{que_NAME:'Q.PRISM.ED810_INVOICE_DATA_RES',rabbit_mq:'Y'})
CREATE(ED810_INVOICE_DATA_RES1:queue{que_NAME:'Q.PRISM.ED810_INVOICE_DATA_RES1',rabbit_mq:'Y'})

CREATE (Rabbit1)-[:RMQ]->(Service1)
CREATE (ED810_INVOICE_DATA_RES)-[:HAS_MQ]->(Rabbit1)
CREATE (ED810_INVOICE_DATA_RES1)-[:HAS_MQ]->(Rabbit1)

CREATE(Rabbit2:rabit{que_type:'RABBIT'})
CREATE(ED810_INVOICE_DATA_RES11:queue{que_NAME:'Q.PRISM.ED810_INVOICE_DATA_RES',rabbit_mq:'Y'})
CREATE(ED810_INVOICE_DATA_RES12:queue{que_NAME:'Q.PRISM.ED810_INVOICE_DATA_RES1',rabbit_mq:'Y'})

CREATE (Rabbit2)-[:RMQ]->(Service2)
CREATE (ED810_INVOICE_DATA_RES11)-[:HAS_MQ]->(Rabbit2)
CREATE (ED810_INVOICE_DATA_RES12)-[:HAS_MQ]->(Rabbit2)

CREATE(Rabbit3:rabit{que_type:'RABBIT'})
CREATE (Rabbit3)-[:RMQ]->(Service7)
CREATE(ED810_INVOICE_DATA_RES31:queue{que_NAME:'Q.PRISM.ED810_INVOICE_DATA_RES3',rabbit_mq:'Y'})
CREATE(ED810_INVOICE_DATA_RES32:queue{que_NAME:'Q.PRISM.ED810_INVOICE_DATA_RES4',rabbit_mq:'Y'})
CREATE (ED810_INVOICE_DATA_RES31)-[:HAS_MQ]->(Rabbit3)
CREATE (ED810_INVOICE_DATA_RES32)-[:HAS_MQ]->(Rabbit3)

# Queries

## Mongo Details

1. Get all services which are using mongo (and related collections)
A1. match (c:collection)-[:HAS_COLLECTION]->(m:mongo_db)-[:HAS_MONGO_DB]->(s:service)-[:HAS_SERVICE]->(f:functionality)-[:HAS_FUNCTIONALITY]->(q:division) return f,s,m,c,q

2. Get all services of procurement which are using mongo (and related collections)
A2. match (c:collection)-[:HAS_COLLECTION]->(m:mongo_db)-[:HAS_MONGO_DB]->(s:service)-[:HAS_SERVICE]->(f:functionality)-[:HAS_FUNCTIONALITY]->(q:division) WHERE q.sub_project_name = "Procurement_team" return f,s,m,c,q

3. Get all services of inventory which are using mongo (and related collections)
A3. match (c:collection)-[:HAS_COLLECTION]->(m:mongo_db)-[:HAS_MONGO_DB]->(s:service)-[:HAS_SERVICE]->(f:functionality)-[:HAS_FUNCTIONALITY]->(q:division) WHERE q.sub_project_name = "Inventory_team" return f,s,m,c,q

4. Get all services of Invoice function (procurement) which are using mongo (and related collections)
A4. match (c:collection)-[:HAS_COLLECTION]->(m:mongo_db)-[:HAS_MONGO_DB]->(s:service)-[:HAS_SERVICE]->(f:functionality)-[:HAS_FUNCTIONALITY]->(q:division) WHERE f.func_name = "Invoice"  return f,s,m,c,q

## General Property Details

5. Show Service Owners
A5. MATCH (k:owner)-[r:OWNS]->(s:service)-[:HAS_SERVICE]->(f:functionality)-[:HAS_FUNCTIONALITY]->(q:division) RETURN k,r,s,f,q

6. Show Inventory Service Owners
A6. MATCH (k:owner)-[r:OWNS]->(s:service)-[:HAS_SERVICE]->(f:functionality)-[:HAS_FUNCTIONALITY]->(q:division) WHERE q.sub_project_name = "Inventory_team" RETURN k,r,s,f,q

7. Show Procurement Service Owners
A7. MATCH (k:owner)-[r:OWNS]->(s:service)-[:HAS_SERVICE]->(f:functionality)-[:HAS_FUNCTIONALITY]->(q:division) WHERE q.sub_project_name = "Procurement_team" RETURN k,r,s,f,q

8. Show all Gitlab urls
A8. MATCH (n) WHERE EXISTS(n.code_base) RETURN DISTINCT "node" as entity, n.code_base AS code_base, n.service_name AS service_name UNION ALL MATCH ()-[r]-() WHERE EXISTS(r.code_base) RETURN DISTINCT "relationship" AS entity, r.code_base AS code_base, r.service_name AS service_name

## Rabbit Related

6. Rabbit related
A6. MATCH p=()-[h:HAS_MQ]->(n:rabbit)-[m:RMQ]->(s:service) RETURN n,m,s,h,p

## All services 

9. All services of procurement 
A9. MATCH p=()-[r:HAS_SERVICE]->(f:functionality)-[w:HAS_FUNCTIONALITY]->(q:division) WHERE q.sub_project_name = "Procurement_team"  RETURN p,f,q,w LIMIT 25

10. All services of inventory 
A10. MATCH p=()-[r:HAS_SERVICE]->(f:functionality)-[w:HAS_FUNCTIONALITY]->(q:division) WHERE q.sub_project_name = "Inventory_team"  RETURN p,f,q,w LIMIT 25

11. All services 
A11. MATCH p=()-[r:HAS_SERVICE]->(f:functionality)-[w:HAS_FUNCTIONALITY]->(q:division)

12. Total number of services 
A12. MATCH (n:service) RETURN count(n) LIMIT 25

13. All services of Invoice (Procurement) !!!!
A.13. MATCH p=()-[r:HAS_SERVICE]->(f:functionality)-[w:HAS_FUNCTIONALITY]->(q:division) WHERE f.func_name = "Invoice"  RETURN p,f,q,w LIMIT 25

## Kafka Related Details

14. Show all kafka conusmer services(related producer******) 
A14. match (k:Kafka_group)-[:HAS_KAFKA_GROUP]->(f:Kafka)-[:HAS_KAFKA]->(s:service)-[r:HAS_SERVICE]->(d:functionality)-[w:HAS_FUNCTIONALITY]->(q:division) return k,f,s,d,q

15. Show all Kafka producer services(related consumers)
A15. match (k:Kafka_group)-[:HAS_KAFKA_GROUP]->(f:Kafka)-[:HAS_KAFKA]->(s:service) return k,f,s

16. Show all Kafka consumer services for inventory
A16. match (k:Kafka_group)-[:HAS_KAFKA_GROUP]->(f:Kafka)-[:HAS_KAFKA]->(s:service)-[r:HAS_SERVICE]->(d:functionality)-[w:HAS_FUNCTIONALITY]->(q:division) WHERE q.sub_project_name = "Inventory_team"  RETURN k,f,s,d,w,q LIMIT 25

17. All consumer 
A.17. match (k:Kafka_group)-[:HAS_KAFKA_GROUP]->(f:Kafka)-[:HAS_KAFKA]->(s:service)-[r:HAS_SERVICE]->(d:functionality)-[w:HAS_FUNCTIONALITY]->(q:division)-[:IS_PROJECT]->(a:Project) WHERE k.group = "consumer" return k,f,s,d,q,a

18. All producers
A18.  match (k:Kafka_group)-[:HAS_KAFKA_GROUP]->(f:Kafka)-[:HAS_KAFKA]->(s:service)-[r:HAS_SERVICE]->(d:functionality)-[w:HAS_FUNCTIONALITY]->(q:division)-[:IS_PROJECT]->(a:Project) WHERE k.group = “producer” return k,f,s,d,q,a

19.  Show all Kafka producer services for inventory
A19. match (k:Kafka_group)-[:HAS_KAFKA_GROUP]->(f:Kafka)-[:HAS_KAFKA]->(s:service)-[r:HAS_SERVICE]->(d:functionality)-[w:HAS_FUNCTIONALITY]->(q:division) WHERE q.sub_project_name = "Inventory_team"  RETURN k,f,s,d,w,q LIMIT 25

20. Show all Kafka consumer services for procurement
A20. match (k:Kafka_group)-[:HAS_KAFKA_GROUP]->(f:Kafka)-[:HAS_KAFKA]->(s:service)-[r:HAS_SERVICE]->(d:functionality)-[w:HAS_FUNCTIONALITY]->(q:division) WHERE q.sub_project_name = "Procurement_team"  RETURN k,f,s,d,w,q LIMIT 25

21. Show all Kafka producer services for procurement
A21. match (k:Kafka_group)-[:HAS_KAFKA_GROUP]->(f:Kafka)-[:HAS_KAFKA]->(s:service)-[r:HAS_SERVICE]->(d:functionality)-[w:HAS_FUNCTIONALITY]->(q:division) WHERE q.sub_project_name = "Procurement_team"  RETURN k,f,s,d,w,q LIMIT 25

22. Showing all kafka whether its consumer or producer or both with Details.
A22. MATCH (n) WHERE EXISTS(n.produce_or_consume) RETURN DISTINCT "node" as entity, n.produce_or_consume AS produce_or_consume, n.Kafka_topic_name AS Kafka_topic_name LIMIT 25 UNION ALL MATCH ()-[r]-() WHERE EXISTS(r.produce_or_consume) RETURN DISTINCT "relationship" AS entity, r.produce_or_consume AS produce_or_consume, r.Kafka_topic_name AS Kafka_topic_name LIMIT 25

23. Kafka details of a particular service
A23. match (k:Kafka_group)-[:HAS_KAFKA_GROUP]->(f:Kafka)-[:HAS_KAFKA]->(s:service)-[r:HAS_SERVICE]->(d:functionality)-[w:HAS_FUNCTIONALITY]->(q:division) WHERE s.service_name="XXIAP012-Invoice-Outbound-payment-update-service"  RETURN k,f,s,d,w,q

## Oracle Related

24. Which services use Oracle DB
A24. MATCH (o:oracle_db)-[:HAS_ORACLE_DB]->(s:service)-[:HAS_SERVICE]->(d:functionality)-[w:HAS_FUNCTIONALITY]->(q:division) RETURN o,s,d,q LIMIT 25

25. Which inventory services use Oracle DB
A25. MATCH (o:oracle_db)-[:HAS_ORACLE_DB]->(s:service)-[:HAS_SERVICE]->(d:functionality)-[w:HAS_FUNCTIONALITY]->(q:division) WHERE q.sub_project_name = "Inventory_team" RETURN o,s,d,q LIMIT 25

26. Which procurement services use Oracle DB
A26. MATCH (o:oracle_db)-[:HAS_ORACLE_DB]->(s:service)-[:HAS_SERVICE]->(d:functionality)-[w:HAS_FUNCTIONALITY]->(q:division) WHERE q.sub_project_name = "Procurement_team" RETURN o,s,d,q LIMIT 25

27. Show all tables of services which use oracle db 
A27. MATCH p=(k:Oracletable)-[r:FOR_ORACLE_DB_Table]->(o:oracle_db)-[:HAS_ORACLE_DB]->(s:service)-[:HAS_SERVICE]->(d:functionality)-[w:HAS_FUNCTIONALITY]->(q:division) RETURN k,r,o,s,d,q LIMIT 25

28. Show all tables of inventory services which use oracle db 
A28. MATCH p=(k:Oracletable)-[r:FOR_ORACLE_DB_Table]->(o:oracle_db)-[:HAS_ORACLE_DB]->(s:service)-[:HAS_SERVICE]->(d:functionality)-[w:HAS_FUNCTIONALITY]->(q:division) WHERE q.sub_project_name = "Procurement_team" RETURN k,r,o,s,d,q LIMIT 25

29. Show all tables of procurement services which use oracle db 
A29. MATCH p=(k:Oracletable)-[r:FOR_ORACLE_DB_Table]->(o:oracle_db)-[:HAS_ORACLE_DB]->(s:service)-[:HAS_SERVICE]->(d:functionality)-[w:HAS_FUNCTIONALITY]->(q:division) WHERE q.sub_project_name = "Inventory_team" RETURN k,r,o,s,d,q LIMIT 25

30. Show all procedures of services that use oracle db 
A30. MATCH p=(k:Procedure)-[r:FOR_ORACLE_DB]->(o:oracle_db)-[:HAS_ORACLE_DB]->(s:service)-[:HAS_SERVICE]->(d:functionality)-[w:HAS_FUNCTIONALITY]->(q:division) RETURN k,r,o,s,d,q LIMIT 25

31. Show all procedures of inventory services that use oracle db 
A31. MATCH p=(k:Procedure)-[r:FOR_ORACLE_DB]->(o:oracle_db)-[:HAS_ORACLE_DB]->(s:service)-[:HAS_SERVICE]->(d:functionality)-[w:HAS_FUNCTIONALITY]->(q:division) WHERE q.sub_project_name = "Inventory_team" RETURN k,r,o,s,d,q LIMIT 25

32. Show all procedures of Procurement services that use oracle db 
A32. MATCH p=(k:Procedure)-[r:FOR_ORACLE_DB]->(o:oracle_db)-[:HAS_ORACLE_DB]->(s:service)-[:HAS_SERVICE]->(d:functionality)-[w:HAS_FUNCTIONALITY]->(q:division) WHERE q.sub_project_name = "Procurement_team" RETURN k,r,o,s,d,q LIMIT 25
