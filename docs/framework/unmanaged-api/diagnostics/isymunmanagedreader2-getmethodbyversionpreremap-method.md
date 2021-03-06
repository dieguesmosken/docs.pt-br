---
title: Método ISymUnmanagedReader2::GetMethodByVersionPreRemap
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodByVersionPreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodByVersionPreRemap
helpviewer_keywords:
- GetMethodByVersionPreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetMethodByVersionPreRemap method [.NET Framework debugging]
ms.assetid: 0d144ed4-bdb0-4cac-960c-cb90f4dca173
topic_type:
- apiref
ms.openlocfilehash: b12ecfdaf7c90589ce2e96b39f7437444cb91b09
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615417"
---
# <a name="isymunmanagedreader2getmethodbyversionpreremap-method"></a>Método ISymUnmanagedReader2::GetMethodByVersionPreRemap
Obtém um método de leitor de símbolo, dado um token de método e um número de versão de edição e continuação. Os números de versão começam em 1 e são incrementados cada vez que o método é alterado como resultado de uma operação de edição e continuação.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetMethodByVersionPreRemap(  
    [in]  mdMethodDef token,  
    [in]  int version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a>Parâmetros  
 `token`  
 no O token de metadados do método.  
  
 `version`  
 no A versão do método.  
  
 `pRetVal`  
 fora Um ponteiro para a interface [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) retornada.  
  
## <a name="return-value"></a>Valor retornado  
 S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** CorSym. idl. CorSym. h  
  
## <a name="see-also"></a>Veja também

- [Interface ISymUnmanagedReader2](isymunmanagedreader2-interface.md)
