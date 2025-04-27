def find_shortest_longest_word(kalimat):
    """
    Mencari kata terpendek dan terpanjang dalam sebuah kalimat.

    Args:
        kalimat (str): Kalimat yang akan dianalisis.

    Returns:
        tuple: Tuple berisi kata terpendek dan kata terpanjang.
               Mengembalikan (None, None) jika kalimat kosong.
    """
    # Hilangkan tanda baca dan ubah ke huruf kecil
    import string
    translator = str.maketrans('', '', string.punctuation)
    kalimat = kalimat.translate(translator).lower()

    kata_kata = kalimat.split()

    if not kata_kata:
        return None, None

    terpendek = kata_kata[0]
    terpanjang = kata_kata[0]

    for kata in kata_kata:
        if len(kata) < len(terpendek):
            terpendek = kata
        if len(kata) > len(terpanjang):
            terpanjang = kata

    return terpendek, terpanjang

# Contoh penggunaan
kalimat_input = "red snakes and a black frog in the pool"
terpendek, terpanjang = find_shortest_longest_word(kalimat_input)
print(f"Kalimat: '{kalimat_input}'")
print(f"Kata terpendek: {terpendek}")
print(f"Kata terpanjang: {terpanjang}")

kalimat_lain = input("Masukkan sebuah kalimat: ")
terpendek_lain, terpanjang_lain = find_shortest_longest_word(kalimat_lain)
if terpendek_lain and terpanjang_lain:
    print(f"Kata terpendek: {terpendek_lain}")
    print(f"Kata terpanjang: {terpanjang_lain}")
else:
    print("Kalimat kosong.")
