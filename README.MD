# My YAML Documentation

## __Struktur YAML__
1. Struktur YAML yang valid tersusun atas __associative array__ (pasangan key & value), __list__ (list value) maupun kombinasi antara keduanya. 
2. Value dapat berupa _scalar_ (string, integer, float, etc.), _boolean_ (`true` / `false`), _date_ maupun _timestamp_. 
3. Perlu diperhatikan pula tab/indentasi, gunakan tab/indentasi untuk _nested key_ (key yang berada di dalam associative array atau list).
4. Diperkenankan adanya comments dalam YAML, gunakan tanda pagar (`#`) untuk membuat komentar.

## __Contoh YAML__
   - Associative Array

        ```yaml
        # key: value
        # Contoh
        名前: Riki
        苗字: Setiawan
        大学: True 
        # Atau
        {
            名前: Riki,
            苗字: Setiawan,
            大学: True
        }
        ```

   - List

        ```yaml
        # List - value
        # Contoh
        - 1
        - 2
        - こさき
        - False
        # Atau
        [1, 2, こさき, False]
        ```

   - Reference & Anchor

        ```yaml
        # &variabel // Create variable
        # *variabel // Call variable
        点: &点
            IP: 3.8
            IPK: 3.4

        川崎: *点
        ```

   - Associative Array in List
  
        ```yaml
        [
            {
                名前: ひびき,
                苗字: 北原,
                年: 21
            }
        ]
        # Atau
        - 名前: ひびき
          苗字: 北原
          年: 21
        ```

## __Tambahan__
- Simbol
  - Pemisah antar data dalam satu file `---`
  - (opsional) Penanda akhir dari data `...`
  - Isi dari nilai akan dirender dalam keadaan yang sama sesuai yang ditulis `|`
    
    contoh penulisan:
    ```yaml
    伝言: |
        この番組はご覧の
        スポンサーの提供で
        お送りします。
    ```
    contoh output:
    ```
        この番組はご覧の
        スポンサーの提供で
        お送りします。
    ```
  - Isi dari nilai akan dirender dalam keadaan menjadi kata/kalimat yang memanjang `>`
  
    contoh penulisan:
    ```yaml
    伝言: >
        この番組はご覧の
        スポンサーの提供で
        お送りします。
    ```
    contoh output:
    ```
        この番組はご覧のスポンサーの提供でお送りします。
    ```

## Reference
[Lintang Wisesa](https://gist.github.com/LintangWisesa/af07b9b550c08e5e15f3a71741fb683f)