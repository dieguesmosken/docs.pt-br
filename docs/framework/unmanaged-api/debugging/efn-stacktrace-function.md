---
title: Função _EFN_StackTrace
ms.date: 03/30/2017
api_name:
- _EFN_StackTrace
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_StackTrace
helpviewer_keywords:
- _EFN_StackTrace function [.NET Framework debugging]
ms.assetid: caea7754-867c-4360-a65c-5ced4408fd9d
topic_type:
- apiref
ms.openlocfilehash: a725aa2c0f1fdea523bbf7cba880bc805f855782
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860739"
---
# <a name="_efn_stacktrace-function"></a>\_Função\_EFN StackTrace
Fornece uma representação de texto de um rastreamento de pilha gerenciado e uma `CONTEXT` matriz de registros, um para cada transição entre código gerenciado e não gerenciado.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT CALLBACK _EFN_StackTrace(  
    [in]  PDEBUG_CLIENT  Client,  
    [out] WCHAR          wszTextOut[],  
    [out] size_t         *puiTextLength,  
    [out] LPVOID         pTransitionContexts,  
    [out] size_t         *puiTransitionContextCount,  
    [in]  size_t         uiSizeOfContext,  
    [in]  DWORD          Flags  
);  
```  
  
## <a name="parameters"></a>Parâmetros  
 `Client`  
 no O cliente que está sendo depurado.  
  
 `wszTextOut`  
 fora A representação de texto do rastreamento de pilha.  
  
 `puiTextLength`  
 fora Um ponteiro para o número de caracteres em `wszTextOut`.  
  
 `pTransitionContexts`  
 fora A matriz de contextos de transição.  
  
 `puiTransitionContextCount`  
 fora Um ponteiro para o número de contextos de transição na matriz.  
  
 `uiSizeOfContext`  
 no O tamanho da estrutura de contexto.  
  
 `Flags`  
 no Defina como 0 ou SOS_STACKTRACE_SHOWADDRESSES (0x01) para mostrar o registro de EBP e o ponteiro de pilha Enter (ESP) na frente de `module!functionname` cada linha.  
  
## <a name="remarks"></a>Comentários  
 A `_EFN_StackTrace` estrutura pode ser chamada de uma interface programática do WinDbg. Os parâmetros são usados da seguinte maneira:  
  
- Se `wszTextOut` for NULL e `puiTextLength` não for NULL, a função retornará o comprimento da cadeia `puiTextLength`de caracteres em.  
  
- Se `wszTextOut` não for NULL, a função armazenará texto `wszTextOut` em até o local indicado por `puiTextLength`. Ele retorna com êxito se havia espaço suficiente no buffer ou retorna E_OUTOFMEMORY se o buffer não era longo o suficiente.  
  
- A parte de transição da função será ignorada `pTransitionContexts` se `puiTransitionContextCount` e for nula. Nesse caso, a função fornece chamadores com a saída de texto apenas dos nomes de função.  
  
- Se `pTransitionContexts` for NULL e `puiTransitionContextCount` não for NULL, a função retornará o número necessário de entradas de contexto `puiTransitionContextCount`no.  
  
- Se `pTransitionContexts` não for NULL, a função a tratará como uma matriz de estruturas de `puiTransitionContextCount`comprimento. O tamanho da estrutura é fornecido `uiSizeOfContext`por e deve ser o tamanho de [SimpleContext](stacktrace-simplecontext-structure.md) ou `CONTEXT` para a arquitetura.  
  
- `wszTextOut`é escrito no seguinte formato:  
  
    ```output  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
- Se o deslocamento em Hex for 0x0, nenhum deslocamento será gravado.  
  
- Se não houver nenhum código gerenciado no thread atualmente no contexto, a função retornará SOS_E_NOMANAGEDCODE.  
  
- O `Flags` parâmetro é 0 ou SOS_STACKTRACE_SHOWADDRESSES para ver EBP e ESP na frente de cada `module!functionname` linha. Por padrão, é 0.  
  
    ```cpp  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** SOS_Stacktrace. h  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Depurando funções estáticas globais](debugging-global-static-functions.md)
