# Benchmark Test Results

| # | Benchmark Tasks/Tests | GDART | JBMC | Verdicts by jbmc and gdart | Actual Verdict | Reason | Support SPF | What do we print in SPF |
|---|---|---|---|--------|---|---|---|---|
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
- **All Actual Verdicts**: FALSE (except URLDecoder tests show TRUE in SPF column)
- **Common Exception Types**:
  - String/Array Index Out of Bounds: 8 cases
  - Null Pointer Exception: 3 cases
  - Number Format Exception: 2 cases
  - Unsupported Operation Exception: 3 cases
  - Other: 3 cases

## Tool Performance Overview

### GDART Results:
- Successful detection: 13 cases
- Unknown: 3 cases  
- Timeout: 3 cases

### JBMC Results:
- Successful detection: 13 cases
- Error(42): 6 cases

### SPF Support Status:
- Done: 8 cases
- Already: 3 cases
- Left: 8 cases