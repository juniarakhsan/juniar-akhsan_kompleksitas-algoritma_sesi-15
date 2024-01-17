class Item:
    def __init__(self, name, weight, value):
        self.name = name
        self.weight = weight
        self.value = value

def knapsack_backtracking(items, capacity, current_weight, current_value, selected_items, best_solution):
    # Base case: jika kapasitas habis atau semua barang sudah dipilih
    if current_weight == 0 or not items:
        if current_value > best_solution['value']:
            best_solution['value'] = current_value
            best_solution['items'] = selected_items.copy()
        return

    # Pilih item saat ini
    current_item = items[0]
    if current_weight >= current_item.weight:
        knapsack_backtracking(items[1:], capacity - current_item.weight, 
                              current_weight - current_item.weight, 
                              current_value + current_item.value, 
                              selected_items + [current_item.name], 
                              best_solution)

    # Tidak memilih item saat ini
    knapsack_backtracking(items[1:], capacity, current_weight, current_value, selected_items, best_solution)

# Barang-barang yang dapat dibawa
items = [
    Item('Pedang Ajaib', 5, 12),
    Item('Potion Kekekalan', 3, 8),
    Item('Kompas Magis', 1, 4),
    Item('Mantel Kehancuran', 6, 20),
    Item('Tongkat Cahaya', 2, 6),
]

# Kapasitas maksimal tas
capacity = 10

# Inisialisasi solusi terbaik
best_solution = {'value': 0, 'items': []}

# Panggil algoritma knapsack dengan backtracking
knapsack_backtracking(items, capacity, capacity, 0, [], best_solution)

# Tampilkan hasil
print("Kombinasi barang terbaik:")
for item_name in best_solution['items']:
    print(f"- {item_name}")

print(f"Total nilai yang dapat Anda peroleh: {best_solution['value']}")
