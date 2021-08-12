---
title: 商務用 Skype Server 中的網域準備所進行的變更
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: 下表列出 (Ace) 網域準備在網域根目錄上建立的存取控制專案。 除非另有說明，否則會繼承所有的 Ace。
ms.openlocfilehash: 0e139174bd711476baf54d0a9ba1d2ed6c848c1a0d47b6f020a6139d34be8a80
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349755"
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>商務用 Skype Server 中的網域準備所進行的變更
 
下表列出 (Ace) 網域準備在網域根目錄上建立的存取控制專案。 除非另有說明，否則會繼承所有的 Ace。
  
**加入至網域根目錄的 Ace**

|**Ace**|**RTCUniversal-UserReadOnly-群組**|**RTCUniversal-ServerReadOnly-群組**|**RTCUniversal-UserAdmins**|**RTCHSUniversal-服務**|**已驗證-使用者**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|不繼承 (讀取容器)   <br/> |**是** <br/> |**是** <br/> |否  <br/> |否  <br/> |否  <br/> |
|讀取使用者 PropertySet User-Account-Restrictions  <br/> |**是** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|讀取使用者 PropertySet Personal-Information  <br/> |**是** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|讀取使用者 PropertySet General-Information  <br/> |**是** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|讀取使用者 PropertySet Public-Information  <br/> |**是** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|讀取使用者 PropertySet RTCUserSearchProperty-Set  <br/> |**是** <br/> |否  <br/> |否  <br/> |否  <br/> |**是** <br/> |
|讀取使用者 PropertySet RTCPropertySet  <br/> |**是** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|寫入使用者屬性 Proxy-Addresses  <br/> |否  <br/> |否  <br/> |**是** <br/> |否  <br/> |否  <br/> |
|寫入使用者 PropertySet RTCUserSearchProperty-Set  <br/> |否  <br/> |否  <br/> |**是** <br/> |否  <br/> |否  <br/> |
|寫入使用者 PropertySet RTCPropertySet  <br/> |否  <br/> |否  <br/> |**是** <br/> |否  <br/> |否  <br/> |
|讀取所有 Active Directory 物件的 PropertySet DS-Replication-Get-Changes  <br/> |否  <br/> |否  <br/> |否  <br/> |**是** <br/> |否  <br/> |
   
下表列出網域準備在三個內建容器中建立的 Ace：使用者、電腦和網域控制站。 除非另有說明，否則會繼承所有的 Ace。
**加入至內建容器的 Ace**

|**Ace**|**RTCUniversal-UserReadOnly-群組**|**RTCUniversal-ServerReadOnly-群組**|
|:-----|:-----|:-----|
|不繼承 (讀取容器)   <br/> |**是** <br/> |**是** <br/> |
   

