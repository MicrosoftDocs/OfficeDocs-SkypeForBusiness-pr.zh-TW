---
title: 在商務用 Skype Server 中設定會議加入頁面
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 摘要：瞭解如何在商務用 Skype Server 中設定會議加入頁面。
ms.openlocfilehash: ba90c771321732956b38f5f07af10798829fc54f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58587089"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a>在商務用 Skype Server 中設定會議加入頁面
 
**摘要：** 瞭解如何在商務用 Skype Server 中設定會議加入頁面。
  
當使用者按一下會議邀請中的會議連結時，[會議加入] 頁面便會偵測使用者電腦上是否已安裝商務用 Skype 用戶端。 如果已安裝用戶端，則用戶端會開啟並加入會議。 若未安裝用戶端，則預設會開啟商務用 Skype 用戶端。 
  
## <a name="configure-the-meeting-join-page"></a>設定會議加入頁面

如果您想要允許使用者與其他用戶端版本加入會議，您可以修改會議加入頁面的行為。 這些設定選項已從商務用 Skype Server 控制台中移除，但您使用 Set-CsWebServiceConfiguration Cmdlet 進行設定。
  
**會議加入頁面 Set-CsWebServiceConfiguration 參數**

|**Set-CsWebServiceConfiguration 參數**|**描述**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |此參數已被取代，可搭配內部部署版本的商務用 Skype Server 使用。  <br/> 若設為 True，則使用商務用 Skype 以外的用戶端應用程式加入會議的使用者，將會獲得使用目前用戶端應用程式加入會議的機會。 預設值為 False。  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |此參數已被取代，可搭配內部部署版本的商務用 Skype Server 使用。  <br/>  若設為 True，加入線上會議的替代選項會自動展開並向使用者顯示。 如果設為 False (預設值) ，這些選項將可用，但使用者必須自行顯示選項清單。  <br/> |
   

