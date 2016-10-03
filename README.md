# GIT_JENKINS_PROJECT

Device attempts to get Session.
2. At receiving the get session request the Device Activated Service will notify the backend that
the Device has been activated and forward the request to the DAS Interceptor


(fire and forget).
Internally the notification will be forwarded to the Promotions Service (2a). Since the Device is
activated for the first time there is no Device Certificat


e specified so the DAS Interceptor will
block the request and retrieval of the session will fail (2b)
3. Within the TomTom backend the Promotion Service will determine whether there are pending
promotions and if so invoke Add Product commands on the Service

Bus (3a). The Service bus will
enrich the command (adding the Product details) and forward the command to the Add-on
Module (3b). At the same time the Device will attempt to get an certificate by calling DAS (3).
