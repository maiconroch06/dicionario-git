# Git e GitHub — Guia de uso pelo Git Bash

## Sumário

13. [Introduzindo Branch](#13-introduzindo-branch)
14. [Listando as Branches](#14-listando-as-branches)
15. [Criando e Navegando entre Branches](#15-criando-e-navegando-entre-branches)
16. [Processo de Mesclagem(merge)](#16-processo-de-mesclagem(merge))
17. [Excluindo Branches](#17-excluindo-branches)

---


# 13. [Introduzindo Branch](#sumário)

> Uma branch é basicamente uma linha do tempo paralela do seu projeto. Você pode criar uma branch, fazer modificações, errar à vontade e, quando tudo estiver perfeito, juntar (fazer o merge) com a linha principal (geralmente chamada de main).

---

# 14. [Listando as Branches](#sumário)
> Antes de criar ou mudar de branch, é bom saber onde você está.

### Exibe a branch atual

```bash
git branch
```

### Ver todas as branches (locais e no GitHub):

```bash
git branch -a
```

**Observação:**
A branch com um asterisco (* main) ou em verde é a que você está no momento.

---

# 15. [Criando e Navegando entre Branches](#sumário)

> Existem duas formas principais de lidar com isso: o comando tradicional (git checkout) e o comando moderno (git switch, introduzido para ser mais intuitivo). Vamos focar no moderno, mas é bom saber que ambos fazem a mesma coisa nesse contexto.

### Criar uma nova branch:

```bash
git branch nome-da-branch
```

**Observação:**
Isso cria a branch, mas não muda você para ela.

### Mudar de uma branch para outra:

```bash
git switch nome-da-branch
```

Criar e já mudar para a nova branch (O mais usado no dia a dia):

```bash
git switch -c nome-da-branch
```

---

# 16. [Processo de Mesclagem(merge)](#sumário)

> Quando você termina de trabalhar na sua branch paralela e quer trazer as alterações para a main, você usa o comando de merge.

1. Vá para a branch que vai receber o código (geralmente a main):
```Bash
git switch main
```

2. Execute o merge puxando a branch que você modificou:

```Bash
git merge nome-da-branch
```

**Regra de ouro do Merge:**
Você sempre deve "puxar" as alterações para a branch onde você está.

---

# 17. [Excluindo Branches](#sumário)
> Depois de fazer o merge de uma funcionalidade, a branch dela não é mais necessária e pode ser excluída para manter o repositório limpo.

### Excluir uma branch com segurança:

```Bash
git branch -d nome-da-branch
```
O Git vai impedir a exclusão se você tiver alterações nessa branch que ainda não sofreram merge.

### Forçar a exclusão (Cuidado!):

```Bash
git branch -D nome-da-branch
```

Usa-se o -D maiúsculo quando você testou algo, deu errado e você quer apagar a branch sem salvar nada.

---