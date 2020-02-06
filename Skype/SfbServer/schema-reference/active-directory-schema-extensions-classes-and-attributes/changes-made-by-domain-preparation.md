---
title: 在商務用 Skype Server 中由網域準備所做的變更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: 下表列出網域準備在網域根目錄上建立的存取控制專案（Ace）。 除非另有說明，否則所有 Ace 都是繼承的。
ms.openlocfilehash: 8a087dfbbd8b670467727803f996694a816cc065
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815541"
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>在商務用 Skype Server 中由網域準備所做的變更
 
下表列出網域準備在網域根目錄上建立的存取控制專案（Ace）。 除非另有說明，否則所有 Ace 都是繼承的。
  
**加入到網域根目錄的 Ace**

|**A**|**RTCUniversal-UserReadOnly-群組**|**RTCUniversal-ServerReadOnly-群組**|**RTCUniversal-UserAdmins**|**RTCHSUniversal-服務**|**已驗證-使用者**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|讀取容器（不是繼承的）  <br/> |**是的** <br/> |**是的** <br/> |否  <br/> |否  <br/> |否  <br/> |
|讀取使用者 PropertySet 使用者帳戶-限制  <br/> |**是的** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|閱讀使用者 PropertySet 個人資訊  <br/> |**是的** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|閱讀使用者 PropertySet 一般資訊  <br/> |**是的** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|讀取使用者 PropertySet 公用資訊  <br/> |**是的** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|讀取使用者 PropertySet RTCUserSearchProperty-設定  <br/> |**是的** <br/> |否  <br/> |否  <br/> |否  <br/> |**是** <br/> |
|讀取使用者 PropertySet RTCPropertySet  <br/> |**是的** <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|撰寫使用者屬性 Proxy-位址  <br/> |否  <br/> |否  <br/> |**是** <br/> |否  <br/> |否  <br/> |
|撰寫使用者 PropertySet RTCUserSearchProperty-設定  <br/> |否  <br/> |否  <br/> |**是** <br/> |否  <br/> |否  <br/> |
|撰寫使用者 PropertySet RTCPropertySet  <br/> |否  <br/> |否  <br/> |**是** <br/> |否  <br/> |否  <br/> |
|讀取 PropertySet DS-複製-變更所有 Active Directory 物件  <br/> |否  <br/> |否  <br/> |否  <br/> |**是** <br/> |否  <br/> |
   
下表列出了網域準備在三個內建容器中建立的 Ace：使用者、電腦及網網域控制站。 除非另有說明，否則所有 Ace 都是繼承的。
**加入到內建容器中的 Ace**

|**A**|**RTCUniversal-UserReadOnly-群組**|**RTCUniversal-ServerReadOnly-群組**|
|:-----|:-----|:-----|
|讀取容器（不是繼承的）  <br/> |**是的** <br/> |**是的** <br/> |
   

