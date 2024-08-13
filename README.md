from operaçoe import calcular_media, reprovado, imprimir_reprovados

# Dados dos alunos (exemplo)
alunos = {
    12345: {'nome': 'João Silva', 'notas': [7, 8, 6, 5]},
    67890: {'nome': 'Maria Pereira', 'notas': [9, 10, 9, 8]},
    98765: {'nome': 'Pedro Santos', 'notas': [4, 5, 3, 2]}
}

# Encontrar os alunos reprovados
reprovados = []
for matricula, aluno in alunos.items():
    media = calcular_media(aluno['notas'])
    if reprovado(media):
        reprovados.append(matricula)

# Imprimir os resultados
imprimir_reprovados(alunos, reprovados)

def calcular_media(notas):
    """Calcula a média aritmética das notas.

    Args:
        notas: Uma lista contendo as notas dos quatro bimestres.

    Returns:
        A média aritmética das notas.
    """
    return sum(notas) / len(notas)

def reprovado(media):
    """Verifica se o aluno foi reprovado.

    Args:
        media: A média do aluno.

    Returns:
        True se o aluno estiver reprovado (média < 6), False caso contrário.
    """
    return media < 6

def imprimir_reprovados(alunos, reprovados):
    """Imprime os dados dos alunos reprovados.

    Args:
        alunos: Um dicionário com os dados dos alunos.
        reprovados: Uma lista com as matrículas dos alunos reprovados.
    """
    for matricula in reprovados:
        aluno = alunos[matricula]
        media = calcular_media(aluno['notas'])
        print(f"Aluno Reprovado: {aluno['nome']} - Matrícula: {matricula} - Média Final: {media}")
