---
title: 選取轉譯規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
description: 企業語音要求將所有的撥號字串標準化為 E. 164 格式，以執行反向數位查閱（RNL）。 主幹對等 (亦即關聯的閘道、PBX 或 SIP 主幹) 可能要求號碼要為當地撥號格式。 為了將號碼從 E.164 格式轉譯成當地撥號格式，您可以選擇性地定義一或多個轉譯規則，以操作要求 URI 再將它遞送給主幹對等。 例如，您可以撰寫轉譯規則，從撥號字串的開頭移除 +44 並替換成 0144。
ms.openlocfilehash: 1825b2c234a6d2c0f1ab46ae0e62245ef54c9421
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822106"
---
# <a name="select-translation-rules"></a>選取轉譯規則
 
 企業語音要求將所有的撥號字串標準化為 E. 164 格式，以執行反向數位查閱（RNL）。 主幹對等 (亦即關聯的閘道、PBX 或 SIP 主幹) 可能要求號碼要為當地撥號格式。 為了將號碼從 E.164 格式轉譯成當地撥號格式，您可以選擇性地定義一或多個轉譯規則，以操作要求 URI 再將它遞送給主幹對等。 例如，您可以撰寫轉譯規則，從撥號字串的開頭移除 +44 並替換成 0144。
  
> [!IMPORTANT]
> 將一或多個翻譯規則與企業語音幹線設定關聯的能力，旨在代替在幹線對等上設定翻譯規則的替代方案。 如果您已在中繼對等上設定翻譯規則，則不要將翻譯規則與企業語音幹線配置建立關聯，因為這兩個規則可能會衝突。 
  
若要使用現有的轉譯規則，請按一下清單中的規則，再按一下 **[確定]**。
  
如需使用商務用 Skype Server [控制台] 所能執行的不同程式的詳細資訊，請參閱[管理商務用 Skype server 2015](../../manage/manage.md)。
  

