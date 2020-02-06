---
title: 在商務用 Skype Server 中設定會議加入頁面
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 摘要：瞭解如何在商務用 Skype Server 中設定 [會議加入] 頁面。
ms.openlocfilehash: 7381db4983b5a2c1ec6dccf474f0b381e079e222
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818514"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a>在商務用 Skype Server 中設定會議加入頁面
 
**摘要：** 瞭解如何在商務用 Skype Server 中設定 [會議加入] 頁面。
  
當使用者按一下會議邀請中的會議連結時，[會議加入] 頁面會偵測到使用者電腦上是否已安裝商務用 Skype 用戶端。 如果已安裝用戶端，用戶端會開啟並加入會議。 如果沒有安裝用戶端，則預設會開啟商務用 Skype 用戶端。 
  
## <a name="configure-the-meeting-join-page"></a>設定會議加入頁面

如果您想要允許使用者加入與其他用戶端版本的會議，您可以修改會議加入頁面的行為。 這些設定選項已從商務用 Skype Server 控制台中移除，但您可以使用 CsWebServiceConfiguration Cmdlet 進行設定。
  
**會議加入頁面集-CsWebServiceConfiguration 參數**

|**CsWebServiceConfiguration 參數**|**說明**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |此參數已棄用，可與商務用 Skype Server 的內部部署版本搭配使用。  <br/> 如果設為 True，則使用者使用商務用 Skype 以外的用戶端應用程式加入會議時，系統會提供機會，以使用目前的用戶端應用程式加入會議。 預設值為 False。  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |此參數已棄用，可與商務用 Skype Server 的內部部署版本搭配使用。  <br/>  如果設為 True，則加入線上會議的替代選項會自動展開並向使用者顯示。 如果設定為 False （預設值），則可以使用這些選項，但使用者將必須針對自己顯示選項清單。  <br/> |
   

