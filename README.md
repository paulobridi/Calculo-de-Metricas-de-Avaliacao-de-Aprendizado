# Calculo-de-Metricas-de-Avaliacao-de-Aprendizado

Entendido! Vamos criar um projeto para calcular as métricas de avaliação de aprendizado de máquina com base em uma matriz de confusão. Aqui está um plano inicial para o projeto:

---

### **Plano do Projeto:**
1. **Objetivo:**
   - Implementar funções para calcular as métricas de avaliação de modelos de classificação:
     - **Acurácia**
     - **Sensibilidade (Recall)**
     - **Especificidade**
     - **Precisão**
     - **F-Score**

2. **Entrada:**
   - Valores da matriz de confusão:
     - VP (Verdadeiros Positivos)
     - VN (Verdadeiros Negativos)
     - FP (Falsos Positivos)
     - FN (Falsos Negativos)

3. **Saída:**
   - Valores calculados para cada métrica.

4. **Estrutura do Código:**
   - Criar uma classe chamada `MetricasClassificacao` para encapsular os cálculos.
   - Implementar métodos para cada métrica.
   - Adicionar um método para exibir todas as métricas calculadas.

---

### **Código Inicial:**

```python
class MetricasClassificacao:
    def __init__(self, vp, vn, fp, fn):
        """
        Inicializa a classe com os valores da matriz de confusão.
        :param vp: Verdadeiros Positivos
        :param vn: Verdadeiros Negativos
        :param fp: Falsos Positivos
        :param fn: Falsos Negativos
        """
        self.vp = vp
        self.vn = vn
        self.fp = fp
        self.fn = fn

    def acuracia(self):
        """
        Calcula a acurácia.
        Fórmula: (VP + VN) / (VP + VN + FP + FN)
        """
        total = self.vp + self.vn + self.fp + self.fn
        return (self.vp + self.vn) / total if total != 0 else 0

    def sensibilidade(self):
        """
        Calcula a sensibilidade (Recall).
        Fórmula: VP / (VP + FN)
        """
        return self.vp / (self.vp + self.fn) if (self.vp + self.fn) != 0 else 0

    def especificidade(self):
        """
        Calcula a especificidade.
        Fórmula: VN / (VN + FP)
        """
        return self.vn / (self.vn + self.fp) if (self.vn + self.fp) != 0 else 0

    def precisao(self):
        """
        Calcula a precisão.
        Fórmula: VP / (VP + FP)
        """
        return self.vp / (self.vp + self.fp) if (self.vp + self.fp) != 0 else 0

    def f_score(self):
        """
        Calcula o F-Score.
        Fórmula: 2 * (Precisão * Recall) / (Precisão + Recall)
        """
        precisao = self.precisao()
        recall = self.sensibilidade()
        return 2 * (precisao * recall) / (precisao + recall) if (precisao + recall) != 0 else 0

    def exibir_metricas(self):
        """
        Exibe todas as métricas calculadas.
        """
        print(f"Acurácia: {self.acuracia():.2f}")
        print(f"Sensibilidade (Recall): {self.sensibilidade():.2f}")
        print(f"Especificidade: {self.especificidade():.2f}")
        print(f"Precisão: {self.precisao():.2f}")
        print(f"F-Score: {self.f_score():.2f}")


# Exemplo de uso
if __name__ == "__main__":
    # Valores arbitrários da matriz de confusão
    vp = 50  # Verdadeiros Positivos
    vn = 40  # Verdadeiros Negativos
    fp = 10  # Falsos Positivos
    fn = 5   # Falsos Negativos

    # Criando uma instância da classe
    metricas = MetricasClassificacao(vp, vn, fp, fn)

    # Exibindo as métricas
    metricas.exibir_metricas()
```

---

### **Explicação do Código:**
1. **Classe `MetricasClassificacao`:**
   - Encapsula os cálculos das métricas.
   - Recebe os valores da matriz de confusão no construtor (`__init__`).

2. **Métodos:**
   - Cada método calcula uma métrica específica com base nas fórmulas fornecidas:
     - **Acurácia:** Mede a proporção de previsões corretas.
     - **Sensibilidade (Recall):** Mede a capacidade de identificar os positivos corretamente.
     - **Especificidade:** Mede a capacidade de identificar os negativos corretamente.
     - **Precisão:** Mede a proporção de positivos previstos corretamente.
     - **F-Score:** Combina precisão e recall em uma única métrica.

3. **Método `exibir_metricas`:**
   - Exibe todas as métricas calculadas com duas casas decimais.

4. **Exemplo de uso:**
   - Valores arbitrários da matriz de confusão são usados para demonstrar o funcionamento.

---

### **Saída Esperada (com os valores do exemplo):**
```
Acurácia: 0.90
Sensibilidade (Recall): 0.91
Especificidade: 0.80
Precisão: 0.83
F-Score: 0.87
```

---

### Próximos Passos:
1. Teste o código com diferentes valores de matriz de confusão.
2. Adapte o código conforme necessário para atender a requisitos específicos do projeto.

Se precisar de mais ajuda ou ajustes, é só avisar! 🚀
