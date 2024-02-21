# Lab Report 3

---

## Part 1 - Bugs

```java
@Test  // Test that fails with existing lab3 implementation
public void testReverseEvenNumElements() {
  int[] input = { 1, 2, 3, 4 };
  assertArrayEquals(new int[] { 4, 3, 2, 1 }, ArrayExamples.reversed(input));
}

@Test // Test that passes with existing lab3 implementation
public void testReverseNoElements() {
  int[] input = { };
  assertArrayEquals(new int[] {  }, ArrayExamples.reversed(input));
}
```

![image](https://github.com/AskewParity/cse15l-lab-reports/assets/147351354/9a855c6c-80fc-4e79-9f82-088123fedbda)

The symptom is that the first element of the array is incorrect.

```java
// Buggy Code
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
  for(int i = 0; i < arr.length; i += 1) {
    arr[i] = newArray[arr.length - i - 1];
  }
  return arr;
}

// fixed code
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
  for (int i = 0; i < arr.length; i += 1) {
    newArray[i] = arr[arr.length - i - 1];
  }
  return newArray;
}
```

There were 2 bugs 
- `newArray` wasn't being changed, instead, garbage/default data was being put into the original `arr`
- the original `arr` is being returned instead of `newArray`

These are solved by
- within the for loop, swapping `arr` and `newArray` so that `newArray` is being filled by `arr` in reverse 
- return `newArray`

---


## Part 2 - Researching Commands

All of the following were found using the `man grep` command
### `-C`

```bash
$ grep -r "microscopically distinct" -C 1

./technical/biomed/1471-2121-2-10.txt-          24, 27, 28], often without a clear definition of these
./technical/biomed/1471-2121-2-10.txt:          terms. Microvilli are light microscopically distinct from
./technical/biomed/1471-2121-2-10.txt-          filopodia and retraction fibers [ 29]. Filopodia or
```

recursively searches for "microscopically distinct" and then gives 1 line of "context" (i.e. 1 line before and after the line with a match). Context provides the full picture of why the pattern is used, in a codebase, it would give the function or at least the surrounding code that the pattern is used in.

```bash
$ grep -r "micron syringe" -C 3

./1471-2091-3-4.txt-          g/mol. Q-Sepharose Fast Flow was purchased from Amersham
./1471-2091-3-4.txt-          Pharmacia Biotech. Nitrocefin was purchased from Becton
./1471-2091-3-4.txt-          Dickinson, and solutions of nitrocefin were filtered
./1471-2091-3-4.txt:          through a Fisherbrand 0.45 micron syringe filter.
./1471-2091-3-4.txt-          Cefaclor, cefoxitin, and cephalothin were purchased from
./1471-2091-3-4.txt-          Sigma; penicillin G and ampicillin were purchased from
./1471-2091-3-4.txt-          Fisher. Imipenem, meropenem, and biapenem were generously

```

recursively searches for "micron syringe" and then gives 3 line of "context" (i.e. 3 line before and after the line with a match). Context provides the full picture of why the pattern is used, in a codebase, it would give the function or at least the surrounding code that the pattern is used in.


### `--exclude`

```bash
$ grep -r "microchip" --exclude="*/plos/*" 
./technical/biomed/1471-2164-3-7.txt:        microchips [ 17 ] , and massive parallel signature
```
recursively searches the directory for "microchip", but exlcudes everything from the `plos` directory (it turns out the majority of results are from `plos`). This enables the search to be limited to the range of files that are nessisary to check through (i.e. if you know some behavior came from certain files).

```bash
$ grep -r "microchip" --exclude="*/biomed/*"

./technical/plos/pmed.0020182.txt:        the development of a novel microchip-based detection system for measuring analytes such as
./technical/plos/pmed.0020182.txt:        plastic microchip, which is housed in a miniature flow cell. Microfluidic channels deliver
./technical/plos/pmed.0020182.txt:        infection in resource-constrained settings. We show that a microchip-based system can
./technical/plos/pmed.0020182.txt:          anticoagulant). All samples were run on the microchip on the day of blood collection.
./technical/plos/pmed.0020182.txt:          The accuracy of the microchip-based CD4 counting system was determined by comparing
./technical/plos/pmed.0020182.txt:        To assess the analytical validity of the membrane-based microchip system, we first
./technical/plos/pmed.0020182.txt:        analyzer (â€œdual-platformâ€ flow cytometry). The microchip
./technical/plos/pmed.0020182.txt:        We next tested this rapid, whole blood microchip assay in a series of samples acquired
./technical/plos/pmed.0020182.txt:        We compared results from our microchip assay with results available from flow cytometry,
./technical/plos/pmed.0020182.txt:        CD4 counts measured by our microchip assay and those measured by flow cytometry.
./technical/plos/pmed.0020182.txt:        Agreement, bias, and correlations between the microchip method and flow cytometry are
./technical/plos/pmed.0020182.txt:        measuring CD4 cell counts can be accurately quantified using the microchip method, and that
./technical/plos/pmed.0020182.txt:        reagent use is minimized in the microchip system, reducing reagent costs by as much as 90%.
./technical/plos/pmed.0020182.txt:        microchip CD4 assay is extremely rapid. CD4 results in the prototype system described here
./technical/plos/pmed.0020182.txt:        consumption for the microchip system can be reduced by a similar factor relative to flow
./technical/plos/pmed.0020182.txt:        most urgent need in HIV diagnostics for resource-poor settings, the microchip platform is
./technical/plos/pmed.0020182.txt:        membrane described here with the previously reported microchip arrays, cellular assays like
```

recursively searches the directory for "microchip", but exlcudes everything from the `biomed` directory (it turns out the majority of results are from `plos`). This enables the search to be limited to the range of files that are nessisary to check through (i.e. if you know some behavior came from certain files).

### `-n`

```bash
$ grep -rn "microchip"

./technical/plos/pmed.0020182.txt:46:        the development of a novel microchip-based detection system for measuring analytes such as
./technical/plos/pmed.0020182.txt:50:        plastic microchip, which is housed in a miniature flow cell. Microfluidic channels deliver
./technical/plos/pmed.0020182.txt:61:        infection in resource-constrained settings. We show that a microchip-based system can
./technical/plos/pmed.0020182.txt:200:          anticoagulant). All samples were run on the microchip on the day of blood collection.
./technical/plos/pmed.0020182.txt:215:          The accuracy of the microchip-based CD4 counting system was determined by comparing
./technical/plos/pmed.0020182.txt:251:        To assess the analytical validity of the membrane-based microchip system, we first
./technical/plos/pmed.0020182.txt:298:        analyzer (â€œdual-platformâ€ flow cytometry). The microchip
./technical/plos/pmed.0020182.txt:307:        We next tested this rapid, whole blood microchip assay in a series of samples acquired
./technical/plos/pmed.0020182.txt:328:        We compared results from our microchip assay with results available from flow cytometry,
./technical/plos/pmed.0020182.txt:334:        CD4 counts measured by our microchip assay and those measured by flow cytometry.
./technical/plos/pmed.0020182.txt:352:        Agreement, bias, and correlations between the microchip method and flow cytometry are
./technical/plos/pmed.0020182.txt:361:        measuring CD4 cell counts can be accurately quantified using the microchip method, and that
./technical/plos/pmed.0020182.txt:427:        reagent use is minimized in the microchip system, reducing reagent costs by as much as 90%.
./technical/plos/pmed.0020182.txt:429:        microchip CD4 assay is extremely rapid. CD4 results in the prototype system described here
./technical/plos/pmed.0020182.txt:442:        consumption for the microchip system can be reduced by a similar factor relative to flow
./technical/plos/pmed.0020182.txt:447:        most urgent need in HIV diagnostics for resource-poor settings, the microchip platform is
./technical/plos/pmed.0020182.txt:449:        membrane described here with the previously reported microchip arrays, cellular assays like
./technical/biomed/1471-2164-3-7.txt:46:        microchips [ 17 ] , and massive parallel signature
```

It recursively searches for the pattern "microchip", and in the print out, the flag `-n` displays the line number in the file it is at. This could pinpoint where the given pattern is at in a multi-thousand line file, giving the ability to travel to the file and inspect that specific section (maybe for debugging, or for context).

```bash
$ grep -rn "why is"

./technical/government/Gen_Account_Office/pe1019.txt:1784:initial story of what is happening and why is displayed as a
./technical/plos/pmed.0010041.txt:72:        First, why is it that early antiretroviral treatment, even if it does lead to better
```

It recursively searches for the pattern "why is", and in the print out, the flag `-n` displays the line number in the file it is at. This could pinpoint where the given pattern is at in a multi-thousand line file, giving the ability to travel to the file and inspect that specific section (maybe for debugging, or for context).

### `-c`

```bash
$ grep "microscopically distinct" ./technical/biomed/1471-2121-2-10.txt -c

1
```

The command recursively searches for hte pattern "microscopically distainct", but instead of printing out the text, it only counts the number of ocurrances in the file, which in this case is 1.

```bash
$ grep "The" ./technical/biomed/1471-2121-2-10.txt -c                     

51
```

The command recursively searches for hte pattern "The", but instead of printing out the text, it only counts the number of ocurrances in the file, which in this case is 51 times in the file.

