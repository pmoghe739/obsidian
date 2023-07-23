
1. run pamoghe-ecd
2. run flexter locally
3. merge to develop(if version bumo than push snapshots using mvn clean deploy)
4. develop ecd
5. create tag from release
6. merge to release.
7. release ECD
8. release flexter(use the same manifest generated above to run flexter) see any failures
9. ART must already be raised.
10. goto release checklist in console and click my manifest and see that there are no more failures.
11. goto flexter and validate all diffs and sign off report.
12. create report in ART
13. https://go/tdp and search for my manifest and then uncheck flexter runs for success percentage.
14. https://go/console goto release , goto manifest and click deploy.
15. https://go/console goto deploy, identify the manifest click live test.