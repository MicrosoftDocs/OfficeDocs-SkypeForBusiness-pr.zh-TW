---
title: 選取轉譯規則
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
ROBOTS: NOINDEX, NOFOLLOW
description: 企業語音需要將所有撥號字串正常化為 e.164 格式，以執行反向號碼查閱 (RNL) 。 主幹對等 (亦即，關聯的閘道、PBX 或 SIP 主幹) 可能要求號碼要為當地撥號格式。 為了將號碼從 E.164 格式轉譯成當地撥號格式，您可以選用定義一或多個轉譯規則，先操作要求 URI 再將它遞送給主幹對等。 例如，您可以撰寫轉譯規則，從撥號字串的開頭移除 +44 並替換成 0144。
ms.openlocfilehash: 41c037a80d5d32737b33373a5549a662311438a9
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60760106"
---
# <a name="select-translation-rules"></a>選取轉譯規則
 
 企業語音需要將所有撥號字串正常化為 e.164 格式，以執行反向號碼查閱 (RNL) 。 主幹對等 (亦即，關聯的閘道、PBX 或 SIP 主幹) 可能要求號碼要為當地撥號格式。 為了將號碼從 E.164 格式轉譯成當地撥號格式，您可以選用定義一或多個轉譯規則，先操作要求 URI 再將它遞送給主幹對等。 例如，您可以撰寫轉譯規則，從撥號字串的開頭移除 +44 並替換成 0144。
  
> [!IMPORTANT]
> 將一個或多個轉譯規則與企業語音主幹組態建立關聯的功能，主要是作為在主幹對等上設定轉譯規則的「替代方法」。如果您已在主幹對等上設定了轉譯規則，請不要將轉譯規則與企業語音主幹設定相關聯，因為兩種規則可能會衝突。 
  
若要使用現有的轉譯規則，請按一下清單中的規則，再按一下 **[確定]**。
  
 
  

