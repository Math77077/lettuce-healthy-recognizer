## 📝 Descrição
<!-- Resuma as mudanças que este Pull Request traz. -->
<!-- Exemplo: "Adiciona ablação de data augmentation no treinamento do YOLO11l." -->

## 🔗 Issue Relacionada
<!-- Se houver uma issue aberta, linke-a aqui. Ex: "Closes #12" -->

## 🏷️ Tipo de Mudança
- [ ] 🐛 **Bug fix** (Correção de erro no pipeline)
- [ ] ✨ **Nova Funcionalidade** (Adição de novo modelo, métrica ou análise)
- [ ] 📊 **Engenharia de Dados** (Mudança na divisão do dataset ou pré-processamento)
- [ ] 📚 **Documentação** (Atualização de Readme, marcação do notebook)
- [ ] 🔧 **Refatoração** (Melhoria de código sem mudar lógica de treino/avaliação)

---

## 🧪 Testes Realizados
<!-- Descreva como você validou a mudança em termos de machine learning e processamento. -->
- [ ] **Treinamento Completo** (O modelo convergiu e gerou arquivo `best.pt`)
- [ ] **Inferência de Imagem** (A validação ou script gerou os gráficos de matriz de confusão/mAP)
- [ ] **Inferência de Vídeo** (O script processou o vídeo sem estourar a VRAM)
- [ ] **Apenas Verificação Sintática/Ambiente** (Sem rodar as épocas de treino inteiras)

---

## ⚡ Verificação de Ambiente & GPU
- [ ] A mudança exige bibliotecas externas novas não listadas no `requirements.txt`?
- [ ] A mudança afeta o consumo de memória VRAM (ex: aumento de tamanho de batch)?
    - *Se SIM, documentou o hardware mínimo esperado?*

---

## ✅ Checklist Final
- [ ] O Notebook roda de ponta a ponta sequencialmente.
- [ ] Não comitei dados `.pt`, `.yaml` sensíveis ou datasets gigantes acidentalmente.
- [ ] Removi minha chave de API (Roboflow, WandB, etc) do código.
