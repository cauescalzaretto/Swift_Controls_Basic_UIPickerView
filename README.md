# Swift Controls Basic UIPickerView

**Controla o objeto de interface responsável por exibir um menu vertical de opções.**



@IBOutlet weak var meuPickerView: UIPickerView!

var arrayNomes = ["Felipe", "Lilica", "Josefina", "Garibalda"]

override func viewDidLoad() {
    super.viewDidLoad()

    self.meuPickerView.delegate = self
    self.meuPickerView.dataSource = self
}

////////////////////////////////////////////////////////
// MARK: Métodos de UIPickerViewDataSource
////////////////////////////////////////////////////////

// Método que define a quantidade de colunas (components) em nosso pickerView
func numberOfComponents(in pickerView: UIPickerView) -> Int {
    return 1
}


// Método que define a quantidade de linhas em determinada coluna.
func pickerView(_ pickerView: UIPickerView, numberOfRowsInComponent component: Int) -> Int {
    
    return self.arrayNomes.count
}

////////////////////////////////////////////////////////
// MARK: Métodos de UIPickerViewDelegate
////////////////////////////////////////////////////////

// Método que define os títulos das linhas nos componentes
func pickerView(_ pickerView: UIPickerView, titleForRow row: Int, forComponent component: Int) -> String? {
    return self.arrayNomes[row]
}


func pickerView(_ pickerView: UIPickerView, didSelectRow row: Int, inComponent component: Int) {
    
    print(self.arrayNomes[row])
    
}

override func touchesBegan(_ touches: Set<UITouch>, with event: UIEvent?) {
    print(self.meuPickerView.selectedRow(inComponent: 0))
}

