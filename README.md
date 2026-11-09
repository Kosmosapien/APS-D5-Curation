# D5 Curadoria – NeuralFilters

**GitHub Pages:** https://kosmosapien.github.io/APS-D5-Curation/

Esta página pública contém somente código de interface. As imagens e decisões estão em um **repositório separado e privado**, Kosmosapien/APS-D5-Curation-Data. Não copie fotografias para este repositório.

## Uso no celular
1. Abra https://github.com/settings/personal-access-tokens/new e crie um token *fine-grained* com acesso somente a **APS-D5-Curation-Data**.
2. Permissões do repositório: **Contents: Read-only** e **Issues: Read and write**. Metadata: Read (padrão).
3. Na página de curadoria, insira o token e conecte. Ele fica em sessionStorage, não no código do site.
4. Compare Original, Teacher bruto e Target APS99; toque na imagem para ampliar.
5. Toque em Aprovar, Rejeitar ou Depois. O voto é registrado como comentário em uma issue privada de seu lote; o sincronizador APS102, rodando no PC, o copia para o ledger local. Se o computador estiver desligado, o comentário permanecerá no GitHub até a próxima sincronização.

## Arquivos no computador
- Dataset: `C:\Datasets\APS-Makeup\DatasetV5_10k_20261106`
- Targets novos: `batches\batch_XXX\target_aps99_conditional_v13\`
- Votos, append-only: `curation_aps102\decisions.jsonl`
- Estado de cada lote: `curation_aps102\batch_XXX.json`
- Totais: `curation_aps102\latest_summary.json`
- Estado da sincronização: `curation_aps102\status.json`
- Logs: `logs\aps99_*.log`, `logs\aps101_*.log`, `logs\aps102_*.log`

## Segurança e qualidade
- A decisão visual não é autorização legal de uso comercial, nem habilita treinamento automaticamente.
- 99 jobs originais não produziram raw devido a falhas do detector facial; imagens sem teacher/target aparecem como pendentes e não podem ser aprovadas.
- A interface desativa Aprovar quando o target APS99 não existe; rejeição e anotação continuam possíveis.
- Uma decisão é salva no GitHub antes de avançar. O PC sincroniza a cada ~15 segundos se ligado e conectado.
- As permissões do token permitem comentários e leitura de conteúdo **somente no repositório privado**. Nunca coloque o token no HTML ou no Git.
- Não transformar um repositório privado de imagens em público ou habilitar Pages nele.
