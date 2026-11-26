# Simulação de Malware em Python (Keylogger) – Ambiente Controlado

Este repositório foi desenvolvido como parte de um desafio prático de cibersegurança, utilizando **Python** para simular, em ambiente seguro, o comportamento básico de:

- **Keylogger Simulado**.

# Objetivos do Projeto

- Entender, de forma prática, como keyloggers funcionam em nível básico;
- Simulação e comportamentos em um ambiente controlado, com arquivos de teste;

## Keylogger Simulado (`/keylogger`)

Na pasta [`keylogger/`](./keylogger) está o script de **keylogger simulado**, desenvolvido com `pynput` para fins de estudo.

### Comportamento do script

* Escuta eventos de teclado enquanto o programa está em execução;
* Para teclas comuns (letras, números, símbolos), registra diretamente o caractere;
* Para teclas especiais, faz mapeamentos como:

  * espaço → `" "`
  * enter → quebra de linha `"\n"`
  * tab → `"\t"`
  * backspace → tratado de forma simples no log (ex.: espaço)
  * esc → registrado como `[ESC]`
* Teclas de modificação como `Shift`, `Ctrl`, `Alt`, `CapsLock` e afins podem ser ignoradas para reduzir ruído;
* Tudo é salvo em um arquivo `log.txt`, em codificação `utf-8`, na mesma pasta.

> O objetivo deste módulo é **estudar o funcionamento** de um keylogger em nível básico, **não** criar uma ferramenta furtiva ou para uso real.

## Execução em Ambiente Seguro (Visão Geral)

> Sempre execute este projeto em **máquina de testes** ou **VM**, com arquivos criados especificamente para o laboratório.

### 1. Clonar o repositório

```bash
git clone https://github.com/robernerd/simulador.git
cd simulador-malwares
```

### 2. (Opcional, mas recomendado) Criar ambiente virtual

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Instalar dependências

```bash
pip install cryptography pynput
```

### 4. Keylogger Simulado

* Executar o script em `/keylogger` e observar o conteúdo de `log.txt` sendo preenchido conforme as teclas são pressionadas.

---

## 🧠 Aprendizados

Com este projeto foi possível:

* Visualizar, na prática, como **keyloggers** podem atuar sobre arquivos e entradas de teclado;
* Entender que esses códigos não exploram apenas falhas técnicas, mas também **comportamento humano** (como executar binários desconhecidos);
* Reforçar a importância de:

  * backups,
  * uso de VMs,
  * política de menor privilégio,
  * educação em segurança para usuários finais;

