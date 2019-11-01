---
title: 什麼是緊急位置、地方和通話路由？
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
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
description: '瞭解什麼是緊急位置、地點及緊急通話路由，以及如何規劃並指派給您的使用者。 '
ms.openlocfilehash: ff29f807f0766889db8e6be4305e994bdc9637fe
ms.sourcegitcommit: d0f03b8abccdacb675f1063a7532397fd0e91a58
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2019
ms.locfileid: "37901902"
---
# <a name="what-are-emergency-locations-places-and-call-routing"></a>什麼是緊急位置、地方和通話路由？

當您設定通話方案時，您必須在取得電話號碼或指派給使用者時，將緊急位置指派給每個電話號碼，以便支援緊急通話。 您必須先新增並驗證緊急位置，才能將緊急位置指派給電話號碼。 驗證可確保已辨識緊急位置，且其格式正確，也就是緊急回應服務可以使用的正確格式。 如有需要，您可以在緊急位置中新增一個位置，為使用者提供更具體的位置。 例如，位置可以是連結至特定緊急位置的樓層、翼或辦公室。 雖然緊急位置經過驗證，但不會有。
  
## <a name="what-are-emergency-locations"></a>何謂緊急位置？

使用中的電話號碼必須有緊急位置，視國家/地區而定。 在美國，將數位指派給使用者時，需要緊急位置。 在其他國家/地區（例如歐洲、中東及非洲（EMEA）），當您收到來自團隊的電話號碼，或是從其他服務提供者或承運商轉接給小組時，就需要緊急位置。
  
緊急位置可能是使用 [市政位址]、[街道位址] 或 [有選用的位置] 的實體位址來引用。 它是貴組織的公司位置街道或市政位址。 例如，位址 12345 [*北部] 街道、[雷德蒙]、[98052 華盛頓] （WA））* 是用來將緊急呼叫路由至適當的派單頒發機構，並協助您尋找緊急來電者。 如果您的公司有多個物理業務位置，您可能會需要一個以上的緊急位置。
  
驗證緊急位址時，請務必確認其合法且已正確設定緊急回應服務的格式。 您可以新增並儲存未驗證的緊急位置，但只有已驗證的位置可以與使用者建立關聯。 驗證並儲存緊急位置之後，您可以將它指派給使用者。 若要變更已儲存並驗證的緊急位置，您必須建立一個新的。
  
## <a name="what-are-places"></a>什麼是位置？

位置會與緊急位置產生關聯，以便在建築物中提供更精確的位置。 位置通常是地面、建築物翼或使用者所在的辦公室號碼。 您可以有與緊急位址相關聯的不限制數量的位置。
  
當您將緊急位置指派給使用者時，它實際上是您指派位置時所參照的位置 ID。 位置識別碼包含參照的緊急位址（街道或市政位址）。 對於不需要內建位置的情況，預設位置會隨附在緊急位置。
  
## <a name="what-is-emergency-call-routing"></a>何謂緊急呼叫路由？

當您在派遣緊急第一次回應程式時，會在將緊急呼叫路由至適當的派遣中心期間，使用緊急位置和位置。 當小組使用者撥打電話號碼時，通話如何傳送給服務的公用安全應答點（PSAP）會依國家和地區而有所不同。 在某些國家/地區（例如美國和英國），在將呼叫連接至適當的派遣中心之前，會先進行呼叫，以判斷使用者目前的位置。 在其他國家和地區，通話會直接路由到派遣中心，為與緊急呼叫者相關聯的電話號碼提供服務。
  
## <a name="create-add-and-assign-emergency-locations-and-places-to-your-users"></a>建立、新增及指派緊急位置與使用者的位置

1. **規劃緊急位置**。 第一個步驟是規劃緊急位置。 列出您所有的實際位址。 然後根據這個，判斷是否需要緊急位置的位置，如果是的話，也就是它們的內容。 例如，如果某項企業有三個由四個地面組成的辦公樓，就很可能需要有三個緊急位置，而地面1到4個是每個的位置。
    
2. **新增緊急位置**。 下一步是新增緊急位置。 若要深入瞭解，請參閱[新增、變更或移除組織的緊急位置](add-change-remove-emergency-location-organization.md)。
    
    > [!IMPORTANT]
    > 驗證街道或市政位址涉及確認其合法且格式正確。 部分正確的緊急位址（例如，城市名稱錯誤）可能仍會通過驗證。 驗證程式會使用指定位址的所有部分來判斷它是否包含足夠的資訊，以將呼叫路由至適當的緊急派單中心。 如果是，它會以驗證方式傳回，然後可以指派給電話號碼。
  
3. **取得電話號碼**。 下一步是為您的使用者取得電話號碼。 您可以從 Office 365 取得新的電話號碼，或 [移植]，或將現有的電話號碼轉移到 Office 365 來執行此動作。 若要查看完整的步驟，請參閱[將電話號碼轉接至 Office 365](transfer-phone-numbers-to-office-365.md)。
    
4. **指派電話號碼**。 最後一個步驟是讓使用者撥打及接聽電話。 若要這樣做，您必須為每位使用者指派電話號碼。 請參閱[指派、變更或移除使用者的電話號碼](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user)，以指派電話號碼。

> [!NOTE]
> 如果您需要取得更多的電話號碼，請[聯絡 PSTN 服務台](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)。

    
## <a name="related-topics"></a>相關主題

[通話方案所用的不同類型的電話號碼](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[緊急通話條款及條件](emergency-calling-terms-and-conditions.md)