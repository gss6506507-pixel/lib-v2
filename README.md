# Vaehz UI Library

Uma biblioteca de interface gráfica (UI Library) moderna e elegante para Roblox, desenvolvida com foco em fluidez, animações suaves e design limpo.

## Estrutura da Pasta

Esta pasta está organizada da seguinte forma para facilitar a hospedagem em um repositório GitHub:

```text
VaehzUI/
├── src/
│   └── VaehzUI.lua       -- Código-fonte principal da biblioteca
├── example/
│   └── example.lua       -- Exemplo completo de uso de todos os componentes
└── README.md             -- Documentação de uso e hospedagem
```

## Como Hospedar e Usar

1. **Criar um Repositório no GitHub**:
   - Crie um novo repositório público no GitHub (ex: `VaehzUI`).
   - Envie o conteúdo da pasta `src/` e `example/` para o repositório.

2. **Carregar via `loadstring`**:
   Após enviar para o GitHub, você pode carregar a biblioteca diretamente nos seus scripts utilizando o link **Raw** do arquivo `VaehzUI.lua`:

   ```lua
   local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/SEU_USUARIO/VaehzUI/main/src/VaehzUI.lua"))()
   ```

## Componentes Disponíveis

- **Janela (`CreateWindow`)**: Suporte a título, acentuação de cores, botões de minimizar, fechar e atalhos para YouTube/Discord.
- **Notificações (`Notify`)**: Sistema de alertas flutuantes no canto inferior direito.
- **Abas (`CreateTab`)**: Navegação lateral com ícones e transições suaves.
- **Rótulos (`CreateLabel`)**: Textos informativos.
- **Avisos (`CreateWarning`)**: Caixas de alerta destacadas.
- **Botões (`CreateButton`)**: Botões interativos com efeito hover e animação de clique.
- **Toggles (`CreateToggle`)**: Interruptores liga/desliga animados, com keybind opcional ao lado.

### Keybind das Toggles

O `CreateToggle` aceita `Keybind` como nome da tecla ou `Enum.KeyCode`, além de `KeybindImage` opcional para substituir o ícone padrão (`rbxassetid://121332782788896`). Ao clicar no controle do teclado, a biblioteca entra no modo de captura, move o ícone para a esquerda e mostra `...`; pressione uma tecla para salvar o bind ou `Escape` para cancelar.

```lua
local toggle = Tab:CreateToggle({
    Name = "Enabled",
    Keybind = "F",
    Callback = function(enabled) print(enabled) end,
    KeybindCallback = function(keyCode) print(keyCode and keyCode.Name or "None") end,
})

toggle:SetKeybind("G")
local currentKey = toggle:GetKeybind()
toggle:ClearKeybind()
```

- **Status (`CreateStat`)**: Rótulos estatísticos em formato de chave-valor.
- **Sliders (`CreateSlider`)**: Barras deslizantes numéricas com suporte a toque e mouse.
- **Caixas de Texto (`CreateTextbox`)**: Campos de entrada de texto redimensionáveis.
- **Seletor de Cores (`CreateColorPicker`)**: Seletor HSV interativo integrado.
- **Menus Suspensos (`CreateDropdown`)**: Dropdowns simples ou múltiplos com expansão suave.

## Licença

Distribuído sob a licença MIT. Sinta-se livre para usar e modificar.
