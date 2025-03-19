import tkinter as tk
from tkinter import messagebox

# Função para cadastrar aluno
def cadastrar_aluno():
    nome = entrada_nome.get()
    idade = entrada_idade.get()
    nota = entrada_nota.get()
    
    if nome and idade.isdigit() and nota.replace('.', '', 1).isdigit():
        idade = int(idade)
        nota = float(nota)
        messagebox.showinfo("Cadastro Concluído", f"Aluno: {nome}\nIdade: {idade}\nNota Média: {nota:.2f}")
    else:
        messagebox.showerror("Erro", "Por favor, insira dados válidos.")

# Criando a janela principal
janela = tk.Tk()
janela.title("Cadastro de Aluno")
janela.geometry("300x200")

# Rótulos e entradas
tk.Label(janela, text="Nome do Aluno:").pack()
entrada_nome = tk.Entry(janela)
entrada_nome.pack()

tk.Label(janela, text="Idade:").pack()
entrada_idade = tk.Entry(janela)
entrada_idade.pack()

tk.Label(janela, text="Nota Média:").pack()
entrada_nota = tk.Entry(janela)
entrada_nota.pack()

# Botão de cadastro
tk.Button(janela, text="Cadastrar", command=cadastrar_aluno).pack()

# Iniciar a interface gráfica
janela.mainloop()

****
