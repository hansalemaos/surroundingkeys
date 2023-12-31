# Finds the closest neighboring keys of a given letter on a specific keyboard layout

## pip install surroundingkeys 

#### Tested against Windows 10 / Python 3.10 / Anaconda 

```python
A utility function to find the closest neighboring keys of a given letter on a specific keyboard layout.

Parameters:
-----------
letter : str
	The letter for which to find the neighboring keys.
keyboard : str
	The keyboard layout identifier. Should be one of the identifiers shown when you call show_all_keyboards().

Returns:
--------
dict
	A dictionary containing the neighboring keys of the input letter on the specified keyboard layout.
	The dictionary has the following structure:
	{
		input_letter: {
			'side': [list of letters on the left and right sides],
			'top': [list of letters above the input letter],
			'bottom': [list of letters below the input letter]
		}
	}
	If no neighboring keys are found or the input letter is not available on the specified keyboard layout,
	the corresponding list will be empty.

Example:
--------
	from surroundingkeys import get_next_letters, show_all_keyboards
	for letter in 'Oi, tudo bem?':
		result = get_next_letters(letter=letter, keyboard="kbdbr_1")
		print(result)
		print(letter)
	{'O': {'side': ['I', 'P'], 'top': ['9', '0'], 'bottom': ['K', 'L']}}
	O
	{'i': {'side': ['u', 'o'], 'top': ['8', '9'], 'bottom': ['j', 'k']}}
	i
	{',': {'side': ['m', '.'], 'top': ['k', 'l'], 'bottom': []}}
	,
	{' ': {'side': [], 'top': [], 'bottom': []}}

	{'t': {'side': ['r', 'y'], 'top': ['5', '6'], 'bottom': ['f', 'g']}}
	t
	{'u': {'side': ['y', 'i'], 'top': ['7', '8'], 'bottom': ['h', 'j']}}
	u
	{'d': {'side': ['s', 'f'], 'top': ['e', 'r'], 'bottom': ['x', 'c']}}
	d
	{'o': {'side': ['i', 'p'], 'top': ['9', '0'], 'bottom': ['k', 'l']}}
	o
	{' ': {'side': [], 'top': [], 'bottom': []}}

	{'b': {'side': ['v', 'n'], 'top': ['g', 'h'], 'bottom': []}}
	b
	{'e': {'side': ['w', 'r'], 'top': ['3', '4'], 'bottom': ['s', 'd']}}
	e
	{'m': {'side': ['n', ','], 'top': ['j', 'k'], 'bottom': []}}
	m
	{'?': {'side': [], 'top': [], 'bottom': []}}
	?


Note:
-----
This function uses a cache (LRU cache) to speed up repeated calls with the same inputs.
```