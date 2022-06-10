# svn revert

svn revert . -R

# svn log

Svn log -l3 -v 

# svn diff

Diff between two revisions/changesets 

Svn diff -r 121325:121255 

svn diff --diff-cmd=diff -x -U0

# Revert a changeset

Revert the change made in revision 20:

svn merge -c -20 .

svn merge -c -144104 .

Revert the changeset made in revision 141861

svn merge -c -141861 .

# Apply (merge) the change made in revision 20 and 23

svn merge -c20,23 ^/_your_branch_

# Undo a range

svn merge -r UPREV:LOWREV . 

# Example  
From <https://stackoverflow.com/questions/13330011/how-do-i-revert-an-svn-commit> 

# Svn getting an old password

Find last time password was updated:-

svn log | grep -C5 F10

Then copy the revision prior to the one it was updated at

Then update your already checked out copy to that one 

svn update -r 1543

gpg --decrypt /home/cfinch/svn/sysadmin/docs/config/trunk/root_passwords.txt.gpg | grep New

Index: PAT.126/TR3/positioning-process/resources/config.properties
===================================================================
--- PAT.126/TR3/positioning-process/resources/config.properties (revision 141960)
+++ PAT.126/TR3/positioning-process/resources/config.properties (working copy)
@@ -50,3 +50,6 @@
 srcu_type=s7
 srcu_heartbeat_event_target=SrcuS7
 srcu_heartbeat_event_property=Srcu.HeartbeatCounter
+config.srcu.unified=false
+srcu_s7_address=10.1.220.103
+







Index: PAT.126/site.properties
===================================================================
--- PAT.126/site.properties     (revision 141960)
+++ PAT.126/site.properties     (working copy)
@@ -37 +37 @@
-jdbc.url=jdbc:postgresql://mcrs3/pts_test_11_0_5
+jdbc.url=jdbc:postgresql://mcrs3/pts_11_0_5
@@ -45,0 +46 @@
+config.cycloType=c230
@@ -137,2 +138,8 @@
-bms.srcu0.expectedSoftwareVersion=03.02.03
-bms.srcu0.expectedSoftwareChecksum=6049F434
+#bms.srcu0.expectedSoftwareVersion=03.02.03
+#bms.srcu0.expectedSoftwareChecksum=6049F434
+#bms.srcu0.expectedConfigurationChecksum=0
+#bms.srcu0.expectedHardwareChecksum=2005A04E
+#bms.srcu0.expectedSafetyChecksum=50CEC418
+
+bms.srcu0.expectedSoftwareVersion=03.02.04
+bms.srcu0.expectedSoftwareChecksum=464972D8
@@ -141 +148 @@
-bms.srcu0.expectedSafetyChecksum=50CEC418
+bms.srcu0.expectedSafetyChecksum=E33EC966
@@ -163,2 +170,8 @@
-bms.srcu3.expectedSoftwareVersion=04.00.00
-bms.srcu3.expectedSoftwareChecksum=F81EA049
+#bms.srcu3.expectedSoftwareVersion=04.00.00
+#bms.srcu3.expectedSoftwareChecksum=F81EA049
+#bms.srcu3.expectedConfigurationChecksum=0
+#bms.srcu3.expectedHardwareChecksum=960DBF74
+#bms.srcu3.expectedSafetyChecksum=3010A624
+
+bms.srcu3.expectedSoftwareVersion=05.00.00
+bms.srcu3.expectedSoftwareChecksum=1604DE89
@@ -167,2 +180 @@
-bms.srcu3.expectedSafetyChecksum=3010A624
-
+bms.srcu3.expectedSafetyChecksum=3D419EB9
Index: PAT.126/TR1/scanalgo.csv
===================================================================
--- PAT.126/TR1/scanalgo.csv    (revision 141960)
+++ PAT.126/TR1/scanalgo.csv    (working copy)
@@ -1 +1 @@
-#Version:11.0.0
+#Version:11.0.3.2
Index: PAT.126/TR2/scanalgo.csv
===================================================================
--- PAT.126/TR2/scanalgo.csv    (revision 141960)
+++ PAT.126/TR2/scanalgo.csv    (working copy)
@@ -1 +1 @@
-#Version:11.0.0
+#Version:11.0.3.2
Index: PAT.126/TR3/scanalgo.csv
===================================================================
--- PAT.126/TR3/scanalgo.csv    (revision 141960)
+++ PAT.126/TR3/scanalgo.csv    (working copy)
@@ -1 +1 @@
-#Version:11.0.0
+#Version:11.0.3.2