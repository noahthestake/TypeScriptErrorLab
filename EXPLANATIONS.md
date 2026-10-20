# Error explanations

For each error, paste the TypeScript message from the Problems panel. Then write one or two plain sentences: what TypeScript was complaining about, and what you changed.

Example (not one of the ten):

> **Message:** Type 'string' is not assignable to type 'number'.
>
> **Explanation:** The variable was declared as a number, but `"3"` in quotes is a string. I removed the quotes so the value is the number `3`.

## 1. Caught button

**Message:** Argument of type 'string' is not assignable to parameter of type 'number'.

**Explanation:** The ID was passed as a string, but the "rememberCaught()" function requires a number. So putting "rawID" in "Number()" converts it the string to a number to fix the error.

## 2. Look up, number line

**Message:** Property 'padStart' does not exist on type 'number'.

**Explanation:** "pokemon.id" is a number, but the "padStart" method only works on strings. So putting "pokemon.id" in "formatNumber()", a function that converts it to a string to fix the error.

## 3. Sort menu

**Message:** Type '"alphabetical"' is not assignable to type '"id" | "name"'.

**Explanation:** "alphabetical" is not one of the string types allowed. So I changed it to the accepted value "name". 

## 4. Match line

**Message:** 'match' is possibly 'undefined'.

**Explanation:** This error is a warning that the search might not find a match, which would leave the variable undefined. Adding a safety that returns "No match" will fix this issue.

## 5. Look up, HP line

**Message:** Property 'baseStat' does not exist on type 'PokemonStat'.

**Explanation:** The code is trying to access 'baseStat', which is not a property of 'PokemonStat'. I replaced it with the correct property 'value'.

## 6. Look up, type line

**Message:** Property 'primaryType' is missing in type '{ id: number; name: string; }' but required in type 'PokemonSummary'.

**Explanation:** The object being returned did not have 'primaryType' property. So I added 'primaryType' by getting the first type from the Pokemon's data array.

## 7. Nickname line

**Message:** Type 'string | undefined' is not assignable to type 'string'.

**Explanation:** The nickname could be undefined. With the label guaranteeing a string. I added the "??" operator to use the species name if there is no nickname.

## 8. Card-count badge

**Message:** Type '"empty"' is not assignable to type '"none" | "one" | "many"'.

**Explanation:** "empty" is not one of the allowed types for this function. So I changed it to the correct value of "none".

## 9. Buttons after Look up

**Message:** Argument of type 'string' is not assignable to parameter of type 'boolean'.

**Explanation:** The "setBusy" function takes a boolean, but a string was passed. So I changed the argument to the appropriate boolean.

## 10. Look up panel

**Message:** Argument of type 'Promise<PokemonMeasurement>' is not assignable to parameter of type 'PokemonMeasurement'.

**Explanation:** The "loadMeasurement" function returns a Promise since it fetches data async, but the code wasn't waiting for it to resolve. I added "await" to make sure the Promise is ready before assigning it to the variable.

## Typecheck result

Run these and paste what the second command prints. When every error is fixed, it prints nothing after the `tsc --noEmit` line.

```sh
docker compose exec web bun install
docker compose exec web bun run typecheck
```

```text
$ tsc --noEmit
```
