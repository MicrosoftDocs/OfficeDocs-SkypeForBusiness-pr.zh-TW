---
title: 什麼是緊急位置、位址及呼叫路由？
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
description: '瞭解什麼是緊急位址、位置及緊急通話路由, 以及如何規劃並指派給您的使用者。 '
ms.openlocfilehash: 979fab1cd099d568278efd61d06a3f8a75b04541
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483857"
---
# <a name="what-are-emergency-locations-addresses-and-call-routing"></a>什麼是緊急位置、位址及呼叫路由？

當您在 Office 365 中設定通話方案時, 當您取得電話號碼或將其指派給使用者以支援緊急通話時, 您必須將緊急位址指派給每個電話號碼。 您必須先建立並驗證緊急位址, 然後才能將緊急位址指派給電話號碼。 驗證可確保緊急位址能夠辨識, 而且緊急回應服務可以使用它的正確格式。 您也可以在緊急位址中新增位置, 為使用者提供更具體的位置。 例如, 緊急地點可能是連結至特定緊急位址的樓層、翼或辦公室。 雖然緊急位址已驗證, 但位置並不是。
  
## <a name="what-are-emergency-addresses"></a>什麼是緊急位址？

有效電話號碼必須有緊急位址, 但需要時, 視國家/地區而定。 在美國, 將數位指派給使用者時, 需要緊急位址。 在其他國家/地區 (例如歐洲、中東及非洲 (EMEA)), 當您從 Office 365 取得電話號碼, 或是從其他服務提供者或運營商轉接時, 就需要緊急位址。
  
緊急位址可能會稱為市政位址、街道位址或實體位址。 它是貴組織中公司位置的街道或市政位址。 例如, 位址 12345 [*北部] 街道、[雷德蒙]、[98052 華盛頓] (WA))* 是用來將緊急呼叫路由至適當的派單頒發機構, 並協助您尋找緊急來電者。 如果您的公司有多個物理業務位置, 您可能會需要一個以上的緊急位址。
  
驗證緊急位址時, 請務必確認它是合法且已正確格式化, 以符合緊急回應服務的需要。 您可以建立並儲存未驗證的緊急位址, 但只有經過驗證的位址可以與使用者相關聯。 一旦驗證並儲存緊急位址之後, 就可以將它指派給使用者。 如果您需要變更已儲存驗證的緊急位址, 您需要建立新的緊急位址。
  
## <a name="what-are-emergency-locations"></a>何謂緊急位置？

緊急位置會與緊急位址產生關聯, 以便在建築物中提供更精確的位置。 緊急位置通常是一個樓層、建立翼或使用者所在的辦公室號碼。 您可以有與緊急位址相關聯的不限數量的位置。 
  
當您將緊急位址指派給使用者時, 它實際上是您指派位址時所參照的位置 ID。 位置識別碼包含參照的緊急位址 (街道或市政位址)。 預設緊急位置包含在不需要內建位置的情況下的緊急位址。 
  
## <a name="what-is-emergency-call-routing"></a>何謂緊急呼叫路由？

緊急位址和位置會在向適當的派遣中心派發緊急第一次回應程式時, 用於傳送緊急呼叫的程式中使用。 當小組或商務用 Skype 使用者撥打緊急電話號碼時, 通話如何路由到服務的公用安全回應點 (PSAP) 會依國家/地區而有所不同。 在某些國家/地區 (例如美國和英國), 呼叫將先進行篩選, 以便在將呼叫連線至適當的派遣中心之前, 判斷使用者的目前位置。 在其他國家/地區, 通話會直接路由至派遣中心, 為與緊急呼叫者相關聯的電話號碼提供服務。
  
## <a name="create-add-and-assign-emergency-locations-and-addresses-to-your-users"></a>建立、新增並指派緊急位置與位址至使用者

1. **規劃緊急位置**。 第一個步驟是規劃緊急位置。 您需要列出所有的實際位址。 然後根據這個, 判斷緊急位址的位置是否需要, 以及它們的內容為何。 例如, 如果公司的3個辦公室建築物都有4個地面, 就很可能必須有3個緊急位址, 而地面1-4 列為每一個位置。
    
2. **建立並驗證緊急位置**。 下一步是建立並驗證您的緊急位址。 當您建立緊急位址時, 您可以進行驗證。 若要建立緊急位址, 請參閱[新增或移除組織的緊急位址](/SkypeForBusiness/what-are-calling-plans-in-office-365/add-or-remove-an-emergency-address-for-your-organization)。
    
    > [!IMPORTANT]
    > 驗證街道或市政位址涉及確認其合法且格式正確。 部分正確的緊急位址 (例如, 城市名稱錯誤) 可能仍會通過驗證。 驗證程式會使用指定位址的所有部分來判斷它是否包含足夠的資訊, 以將呼叫路由至適當的緊急派單中心。 如果是, 它會以驗證方式傳回, 然後可以指派給電話號碼。 
  
3. **取得電話號碼**。 下一步是為您的使用者取得電話號碼。 您可以從 Office 365 取得新的電話號碼, 或 [移植], 或將現有的電話號碼轉移到 Office 365 來執行此動作。 若要查看完整的步驟, 請參閱[將電話號碼轉接至 Office 365](transfer-phone-numbers-to-office-365.md)。
    
4. **指派電話號碼**。 最後一個步驟是讓使用者撥打及接聽電話。 若要這樣做, 您必須為每位使用者指派電話號碼。 請參閱[指派、變更或移除使用者的電話號碼](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user), 以指派電話號碼。

> [!NOTE]
> 如果您需要取得更多的電話號碼, 請[聯絡商務產品支援-系統管理協助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

    
## <a name="related-topics"></a>相關主題
[什麼是位址驗證？](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[通話方案所用的不同類型的電話號碼](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[緊急通話條款與條件](emergency-calling-terms-and-conditions.md)

[商務用 Skype Online: 緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

