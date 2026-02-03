# Orquestrador de Desenvolvimento Autônomo

Sistema de desenvolvimento autônomo que executa iterações a cada 15 minutos, implementando features, testando e mantendo contexto persistente.

## Como Funciona

O orquestrador lê `prompt.md` (seus objetivos), executa desenvolvimento incremental, testa com agentes virtuais e atualiza `context.md` com o progresso.

## Estrutura de Arquivos

```
├── system_prompt.md    # Instruções do orquestrador
├── prompt.md           # Seus objetivos e requisitos
├── context.md          # Estado atual do projeto
├── agents/             # Agentes de teste virtuais
└── [código do projeto] # Arquivos implementados
```

## Uso

```bash
kiro --system system_prompt.md --input "Execute uma iteração. Leia prompt.md, context.md e agents/. Implemente, teste e atualize os arquivos."
```

## Fluxo de Iteração

1. **Leitura**: Lê `prompt.md`, `context.md` e `agents/`
2. **Planejamento**: Decide próxima ação prioritária
3. **Execução**: Implementa código com commits atômicos
4. **Testes**: Executa agentes de teste específicos
5. **Atualização**: Atualiza `context.md` e `agents/`

## Versionamento Git

- Commits atômicos: `tipo: descrição`
- Tipos: `feat`, `fix`, `refactor`, `test`, `docs`, `chore`
- Branches para features: `feature/nome`
- Merges apenas com testes passando

## Personalização

Edite `prompt.md` para mudar objetivos. O orquestrador detectará e ajustará automaticamente.
