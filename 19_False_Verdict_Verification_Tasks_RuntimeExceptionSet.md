# Benchmark Test Results

| # | Benchmark Tasks/Tests | GDART | JBMC | Verdicts by jbmc and gdart | Actual Verdict | Reason | Support SPF | What do we print in SPF |
|---|---|---|---|---|---|---|---|---|
| 1 | StringValueOf03.yml | Stringindexoutofbounds | Stringindexoutofbounds | for both correct-unconfirmed - false | FALSE | because of charAt() | done | FALSE |
| 2 | StringBuilderChars05.yml | Stringindexoutofbounds | Stringindexoutofbounds | for both FALSE | FALSE | because of setCharAt() | left | unknown |
| 3 | StringBuilderChars03.yml | Stringindexoutofbounds | NO EXCEPTION | true for jbmc and false (correct-unconfirmed for gdart) | FALSE | because of charAt() | done | FALSE |
| 4 | StringValueOf08.yml | unknown | NumberFormatException | unknown for gdart and false (correct-unconfirmed for jbmc) | FALSE | because of parseFloat() | left | unknown |
| 5 | StaticCharMethods05.yml | TIMEOUT | InputMismatchException | TIMEOUT for gdart and false (correct-unconfirmed for jbmc) | FALSE | because of Scanner class | left | unknown |
| 6 | StringMiscellaneous03.yml | TIMEOUT | StringIndexOutOfBoundsException | TIMEOUT for gdart and false (correct-unconfirmed for jbmc) | FALSE | because of charAt() | done | FALSE |
| 7 | SubString03.yml | Stringindexoutofbounds | Stringindexoutofbounds | for both FALSE | FALSE | because of subString() | done | FALSE |
| 8 | SubString02.yml | Stringindexoutofbounds | Stringindexoutofbounds | for both FALSE | FALSE | because of subString() | done | FALSE |
| 9 | StringValueOf02.yml | StringIndexOutOfBoundsException | StringIndexOutOfBoundsException | correct-unconfirmed - false | FALSE | because of charAt() | done | FALSE |
| 10 | StringValueOf09.yml | unknown | NumberFormatException | unknown for gdart and false (correct-unconfirmed for jbmc) | FALSE | because of parseDouble() | left | unknown |
| 11 | URLDecoder01.yml | TIMEOUT | ERROR(42) | TIMEOUT for gdart and unknown (for jbmc) | FALSE | | left | TRUE |
| 12 | URLDecoder02.yml | TIMEOUT | ERROR(42) | TIMEOUT for gdart and unknown (for jbmc) | FALSE | | left | TRUE |
| 13 | ExException_false.yml | NullPointerException | NullPointerException | FALSE for gdart and false (correct-unconfirmed for jbmc) | FALSE | | Already | FALSE |
| 14 | nanoxml_prop3.yml | UnsupportedOperationException | ERROR(42) | unknown for both | FALSE | | left | unknown |
| 15 | nanoxml_prop2.yml | UnsupportedOperationException | ERROR(42) | unknown for both | FALSE | | left | unknown |
| 16 | nanoxml_prop1.yml | UnsupportedOperationException | ERROR(42) | unknown for both | FALSE | | left | unknown |
| 17 | Arrays10.yml | Arrayindexoutofbounds | ArrayIndexOutOfBoundsException | for both FALSE | FALSE | | already | FALSE |
| 18 | StrongUpdates5.yml | NullPointerException | NullPointerException | for both correct-unconfirmed - false | FALSE | | already | FALSE |
| 19 | Collections9.yml | IndexOutOfBoundsException | IndexOutOfBoundsException | for both correct-unconfirmed - false | FALSE | | already | FALSE |

## Summary Statistics

- **Total Test Cases**: 19
- **All Actual Verdicts**: FALSE in the RuntimeException Mode


### GDART Results:
https://sv-comp.sosy-lab.org/2025/results/results-verified/gdart.2024-12-05_09-57-26.results.SV-COMP25_runtime-exception.RuntimeException-Java.xml.bz2.fixed.xml.bz2.table.html#/table?filter=id(values(,false))

### JBMC Results:
https://sv-comp.sosy-lab.org/2025/results/results-verified/jbmc.2024-12-05_11-32-28.results.SV-COMP25_runtime-exception.RuntimeException-Java.xml.bz2.fixed.xml.bz2.table.html#/table?filter=id(values(,false))

### SPF Support Status:
- Done: 8 cases
- Already: 3 cases
- Left: 8 cases