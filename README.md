# Teste01
Calculadora de Energia 

Sobre o Projeito.

⚡ Este sistema foi desenvolvido para auxiliar no controle doméstico de gastos elétricos.
O objetivo é permitir que qualquer usuário descubra o impacto financeiro de seus aparelhos
de forma rápida e visual, transformando um script de terminal em um aplicativo executável para Windows.



🛠️ Linguagem: Python 3.14.3.

Interface Gráfica: Tkinter (biblioteca nativa para janelas).

Compilação: PyInstaller (para gerar o arquivo .exe).


🧮 Fórmula de Cálculo:
O sistema utiliza a fórmula padrão de conversão de Watts para Quilowatt-hora (kWh) mensal, considerando um ciclo de 30 dias


Consumo Mensal (kWh) = Potência (W) x Horas de Uso Diário x 30 Dias
                       _____________________________________________

                                       1000


🚀 Como Executar o Programa:
Baixe o arquivo Teste01.exe através do link compartilhado:
LINK: https://drive.google.com/file/d/1gOViIgk17g8Dk0mLhHR-Va-2F13ZrfNT/view?usp=sharing




import tkinter as tk
from tkinter import messagebox

def calcular():
    try:
        # Pega os dados que você antes digitava no terminal 
        nome = entry_nome.get()
        potencia = float(entry_potencia.get())
        horas = float(entry_horas.get())
        
        # A fórmula do seu script original: (W * Horas * 30 dias) / 1000 
        consumo_mensal = (potencia * horas * 30) / 1000
        
        # Exibe o resultado na tela 
        label_res.config(text=f"Aparelho: {nome}\nConsumo: {consumo_mensal:.2f} kWh", fg="blue")
    except ValueError:
        messagebox.showerror("Erro", "Por favor, use apenas números em Potência e Tempo.")

# Configuração da Janela
app = tk.Tk()
app.title("Calculadora de Energia")
app.geometry("350x300")

# Elementos da Interface
tk.Label(app, text="Nome do Aparelho:").pack(pady=5)
entry_nome = tk.Entry(app)
entry_nome.pack()

tk.Label(app, text="Potência (Watts):").pack(pady=5)
entry_potencia = tk.Entry(app)
entry_potencia.pack()

tk.Label(app, text="Uso Diário (Horas):").pack(pady=5)
entry_horas = tk.Entry(app)
entry_horas.pack()

tk.Button(app, text="Calcular Consumo", command=calcular, bg="green", fg="white").pack(pady=20)

label_res = tk.Label(app, text="", font=("Arial", 10, "bold"))
label_res.pack()

app.mainloop()
