---
title: 您可以取得多少電話號碼？
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: conceptual
ms.assetid: 61dfb27c-5bfa-4481-a930-9c026e73ff3a
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.phonenumbers.searchacquire.tooltip.quantity
- seo-marvel-mar2020
description: 瞭解您可以取得多少電話號碼Microsoft Teams號碼類型，以及您擁有多少授權。
ms.openlocfilehash: ecd3eacc978d81bddc67b64b9e2480bba950aa1f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092221"
---
# <a name="how-many-phone-numbers-can-you-get"></a>您可以取得多少電話號碼？

當您尋找及取得貴組織的電話號碼時，您可以取得比已指派授權更多的電話號碼。 但這取決於您購買和指派的電話號碼類型及授權類型。 您可以按一下[[通話](different-kinds-of-phone-numbers-used-for-calling-plans.md)方案使用的不同電話號碼類型，以找出在通話方案中使用的不同電話號碼Microsoft Teams。
  
您可以在 Microsoft Teams 系統管理中心的取得電話號碼頁面上查看可以取得的電話號碼數目，或者您可以執行[Get-CsOnlineTelephoneNumberAvailableCount](/powershell/module/skype/Get-CsOnlineTelephoneNumberAvailableCount) Cmdlet。
  
> [!IMPORTANT]
> 以下限制不包含您移轉或移轉到 Microsoft 的電話號碼。 
  
## <a name="how-many-phone-numbers-you-can-get"></a>您可以取得多少電話號碼？

||||
|:-----|:-----|:-----|
|**以下是電話號碼的類型** <br/> |**如何取得電話號碼總數？** <br/> |**以下是範例** <br/> |
|使用者 (訂閱) 號碼  <br/> |電話號碼數等於國內通話方案與/或國內及國際通話方案授權總數乘以1.1 + 10 個額外的電話號碼。 <br/> |如果我總共有 50 位使用者擁有國內通話方案及/或國內及國際通話方案，您可以取得 **65** 個電話號碼 **(50 x 1.1 + 10**) 。 <br/> |
|付費服務號碼  <br/> | 電話號碼數量等於通話和音訊會議 **電話系統總數，** 並使用下列專案：  <br/>  如果有 **1-25 個授權** ， **則會提供 5** 個電話號碼。 <br/>  如果有 **26-49 個授權** ， **則提供 10** 個電話號碼。 <br/>  如果有 **50-99 個授權** ， **則提供 20** 個電話號碼。 <br/>  如果有 **100-149 個授權** ， **則會提供 30** 個電話號碼。 <br/>  如果有 **150-199 個授權** ， **則提供 40** 個電話號碼。 <br/>  如果有 **200-499 個授權** ， **則會提供 65** 個電話號碼。 <br/>  如果有 **500-749 個授權** ， **則提供 90** 個電話號碼。 <br/>  如果有 **750-999 個授權** ， **則提供 110** 個電話號碼。 <br/>  如果有 **1，000-1，249** 個授權， **則提供 125** 個電話號碼。 <br/>  如果有 **1，250-1，499** 個授權， **則提供 135** 個電話號碼。 <br/>  如果有 **1，500-1，999** 個授權， **則提供 160** 個電話號碼。 <br/>  如果有 **2，000-2，999** 個授權， **則提供 210** 個電話號碼。 <br/>  如果有 **3，000-6，999** 個授權， **則提供 420** 個電話號碼。 <br/>  如果有 **7，000-9，999** 個授權， **則提供 500** 個電話號碼。 <br/>  如果有 **10，000-14，999** 個授權， **則提供 600** 個電話號碼。 <br/>  如果有 **15，000-19，999** 個授權， **則提供 700** 個電話號碼。 <br/>  如果有 **20，000-49，999** 個授權， **則提供 1000** 個電話號碼。 <br/>  如果授權 **超過 50，000 個，****則提供 1500** 個電話號碼。 <br/> |如果您有總計 **51** 個電話電話系統 **音訊會議授權**，您可以取得 **20 個** 付費服務號碼。 <br/> |
|免付費服務號碼  <br/> | 電話號碼數量等於通話和音訊會議 **電話系統總數，** 並使用下列專案：  <br/>  如果有 **1-25 個授權** ， **則會提供 5** 個電話號碼。 <br/>  如果有 **26-49 個授權** ， **則提供 10** 個電話號碼。 <br/>  如果有 **50-99 個授權** ， **則提供 20** 個電話號碼。 <br/>  如果有 **100-149 個授權** ， **則會提供 30** 個電話號碼。 <br/>  如果有 **150-199 個授權** ， **則提供 40** 個電話號碼。 <br/>  如果有 **200-499 個授權** ， **則會提供 65** 個電話號碼。 <br/>  如果有 **500-749 個授權** ， **則提供 90** 個電話號碼。 <br/>  如果有 **750-999 個授權** ， **則提供 110** 個電話號碼。 <br/>  如果有 **1，000-1，249** 個授權， **則提供 125** 個電話號碼。 <br/>  如果有 **1，250-1，499** 個授權， **則提供 135** 個電話號碼。 <br/>  如果有 **1，500-1，999** 個授權， **則提供 160** 個電話號碼。 <br/>  如果有 **2，000-2，999** 個授權， **則提供 210** 個電話號碼。 <br/>  如果有 **3，000-6，999** 個授權， **則提供 420** 個電話號碼。 <br/>  如果有 **7，000-9，999** 個授權， **則提供 500** 個電話號碼。 <br/>  如果有 **10，000-14，999** 個授權， **則提供 600** 個電話號碼。 <br/>  如果有 **15，000-19，999** 個授權， **則提供 700** 個電話號碼。 <br/>  如果有 **20，000-49，999** 個授權， **則提供 1000** 個電話號碼。 <br/>  如果授權 **超過 50，000 個，****則提供 1500** 個電話號碼。 <br/> |如果您有總計 **1001** 個電話系統音訊會議授權，您可以取得 **125** 個免付費服務號碼。 <br/> <br/> **重要：**[必須支付](set-up-communications-credits-for-your-organization.md)通訊信用額度才能保留及使用免付費電話號碼。          |
   
> [!NOTE]
> 如果您需要取得更多電話號碼，請聯絡商務產品支援人員 [- 系統管理協助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)
  
## <a name="related-topics"></a>相關主題
[移轉電話號碼的常見問題](./phone-number-calling-plans/port-order-overview.md)

[用於通話方案的各種電話號碼](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[緊急通話條款及條件](emergency-calling-terms-and-conditions.md)

[緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
