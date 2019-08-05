---
title: 選取轉譯規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
ROBOTS: NOINDEX, NOFOLLOW
description: 企業語音要求將所有的撥號字串標準化為 E. 164 格式, 以執行反向數位查閱 (RNL)。 主幹對等 (亦即關聯的閘道、PBX 或 SIP 主幹) 可能要求號碼要為當地撥號格式。 為了將號碼從 E.164 格式轉譯成當地撥號格式，您可以選擇性地定義一或多個轉譯規則，以操作要求 URI 再將它遞送給主幹對等。 例如，您可以撰寫轉譯規則，從撥號字串的開頭移除 +44 並替換成 0144。
ms.openlocfilehash: e6df4b2eed01849af7290596bc0e91896e527574
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191770"
---
# <a name="select-translation-rules"></a>選取轉譯規則
 
 企業語音要求將所有的撥號字串標準化為 E. 164 格式, 以執行反向數位查閱 (RNL)。 主幹對等 (亦即關聯的閘道、PBX 或 SIP 主幹) 可能要求號碼要為當地撥號格式。 為了將號碼從 E.164 格式轉譯成當地撥號格式，您可以選擇性地定義一或多個轉譯規則，以操作要求 URI 再將它遞送給主幹對等。 例如，您可以撰寫轉譯規則，從撥號字串的開頭移除 +44 並替換成 0144。
  
> [!IMPORTANT]
> 將一或多個翻譯規則與企業語音幹線設定關聯的能力, 旨在代替在幹線對等上設定翻譯規則的替代方案。 如果您已在中繼對等上設定翻譯規則, 則不要將翻譯規則與企業語音幹線配置建立關聯, 因為這兩個規則可能會衝突。 
  
若要使用現有的轉譯規則，請按一下清單中的規則，再按一下 **[確定]**。
  
 
  

