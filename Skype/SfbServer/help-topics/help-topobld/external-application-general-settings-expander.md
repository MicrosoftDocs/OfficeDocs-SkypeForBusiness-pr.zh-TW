---
title: 外部應用程式一般設定展開工具
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: 若要編輯已定義之信任的應用程式伺服器的屬性，請遵循下列指示。
ms.openlocfilehash: d003a14506ef34f8e37778ec8dd262e269ed93a9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60860330"
---
# <a name="external-application-general-settings-expander"></a>外部應用程式一般設定展開工具
 
若要編輯已定義之信任的應用程式伺服器的屬性，請遵循下列指示。
  
您可以修改兩個區段：
  
> 一般設定
> 
> 下一個躍點設定
    
## <a name="general-settings"></a>一般設定

您可以修改信任的應用程式伺服器集區目前的完整網域名稱 (FQDN)。編輯集區 FQDN 的名稱。新的項目必須有網域名稱系統 (DNS) 主機 (A) 記錄，用戶端或伺服器才能連線至新的集區名稱。
  
如果您需要將組態資料複寫至此集區，請選取 **[對此集區啟用組態資料的複寫]**。如果您不要複寫組態資料，請清除核取記號。
  
## <a name="next-hop-settings"></a>下一個躍點設定

您可以從下拉式清單中選取 [定義的 Enterprise Edition 前端集區] 或 [Standard Edition 前端伺服器]，以指定信任的應用程式伺服器集區的下一個躍點伺服器。 Director 或 Director 集區不能作為信任的應用程式伺服器下一個躍點，因此不會出現在清單中。
  


按一下 **[確定]** 以接受並儲存變更。 按一下 **[取消]** 捨棄變更並結束內容頁面。
  

