# Monitoramento de Consistência Dengue RS (SINAN x GAL)

## 📌 Contexto do Projeto
Este projeto foi desenvolvido durante meu estágio no **CEVS (Centro Estadual de Vigilância em Saúde)**. O objetivo é realizar uma auditoria automatizada entre o sistema de notificações de doenças (SINAN) e o sistema laboratorial (GAL).

## 🕵️ O Problema
A vigilância epidemiológica enfrenta um desafio de "apagão de dados" quando um município realiza o exame laboratorial de um paciente (registrado no GAL), mas esquece de realizar a notificação oficial do caso (registrada no SINAN). Isso impacta diretamente o programa **QUALIFICA**, que mede a eficiência da vigilância municipal.

## ⚙️ Lógica da Solução
O script realiza um cruzamento híbrido:
1. **Pilar de Gestão:** Compara o **Município Notificador** (SINAN) com o **Município Solicitante** (GAL). Se o município pediu o exame, ele deve ter notificado.
2. **Pilar Epidemiológico:** Mantém a visualização do **Município de Residência** para identificar inconsistências cadastrais (ex: pacientes em reservas indígenas).

## 🛠️ Tecnologias
- Python 3.x
- Pandas (Manipulação de dados)
- Openpyxl (Formatação de relatórios Excel)
- DBFread (Leitura de bases legadas do SUS)

## 📅 Periodicidade
O código foi estruturado para execução quinzenal, utilizando janelas de tempo específicas (Ex: Jan/2026).