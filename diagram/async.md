+--------+                                  +--------+          .----.
| Client |                                  |   AS   |         |  RO  |
|Instance+--(1)--- Request Access --------->|        |         |      |
|        |                                  |        |         |      |
|        |<-(2)-- Not Yet Granted (Wait) ---+        |         |      |
|        |                                  |        |<==(3)==>|      |
|        |                                  |        |  AuthN  |      |
|        +--(6)--- Continue Request (A) --->|        |         |      |
|        |                                  |        |<==(4)==>|      |
|        |<-(7)-- Not Yet Granted (Wait) ---+        |  AuthZ  |      |
|        |                                  |        |         |      |
|        |                                  |        |<==(5)==>|      |
|        |                                  |        |Completed|      |
|        |                                  |        |         |      |
|        +--(8)--- Continue Request (B) --->|        |          `----`
|        |                                  |        |
|        |<-(9)------ Grant Access ---------+        |
|        |                                  |        |
|        |                                  |        |     +--------+
|        +--(10)-- Access API ---------------------------->|   RS   |
|        |                                  |        |     |        |
|        |<-(11)-- API Response ---------------------------+        |
|        |                                  |        |     +--------+
+--------+                                  +--------+