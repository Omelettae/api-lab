# api-lab

### Step A1: An input domain model
Characteristic | Blocks | Values in the tests
--- | --- | ---
C1 Value of stars | below 1, 1 to 5 (base), above 5 | 0, 3, 6
C2 Type of stars | whole number (base), decimal, text, missing | 3, 3.5, "3", no field
C3 Pizza | exists (base), does not exist | a new pizza, 999999999
C4 Token | the user's own (base), none, wrong length | from auth, no header, token short


Characteristic | Block | Test
--- | --- | ---
C1 | below 1 | test_stars_out_of_range[0]
C1 | 1 to 5 (base) | test_base_choice_is_saved
C1 | above 5 | test_stars_out_of_range[6]
C2 | whole number (base) | test_base_choice_is_saved
C2 | decimal | test_stars_decimal
C2 | text | test_stars_text
C2 | missing | test_stars_missing
C3 | exists (base) | test_base_choice_is_saved
C3 | does not exist | test_pizza_does_not_exist
C4 | own token (base) | test_base_choice_is_saved
C4 | none | test_token_missing
C4 | wrong length | test_token_too_short