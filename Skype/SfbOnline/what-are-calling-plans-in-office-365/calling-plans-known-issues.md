---
title: 通話方案已知問題
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Calling Plans
description: 瞭解 PSTN 通話的通話方案的已知問題，以及您可以採取的措施。
ms.openlocfilehash: 3a97057f61c154ded83b85becbfcf53dc2b4bc78
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220733"
---
# <a name="calling-plans-known-issues"></a>通話方案已知問題

通話方案是在商務用 Skype Online 中找到的新功能。 下列是目前正在追蹤及主動調查的問題。 在未來組建中更新此功能時，可能會解決這些問題。
  
## <a name="calling-plans-known-issues"></a>通話方案已知問題

|**已知問題**|**註解**|
|:-----|:-----|
|從 Tech Preview 授權轉換到通話方案的生產授權時，不會自動更新授權。  <br/> |您必須先購買新的授權，才能將其指派給您的使用者。 移除使用者的促銷（技術預覽）授權，然後**立即**將新的**國內通話方案**及/或**國內和國際通話方案**授權指派給使用者。 <br/> 如果您要移除並新增多個使用者的授權，您必須從使用 Windows PowerShell 的所有使用者移除授權，然後**立即**使用 Windows powershell 指派所有使用者的授權，這相當重要。 如此一來，就能確保處理大量使用者授權指派時，服務不會中斷。 如需 PowerShell 腳本範例，請參閱[指派商務用 Skype 和 Microsoft 團隊授權](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。  <br/> **注意：** 如果您是針對混合式使用者使用內部部署 PSTN 連線，則*只*需指派**電話系統**授權即可。 您也**不**應該指派語音通話方案。 不過，如果您在 Microsoft 365 或 Office 365 中針對 Microsoft 365 或 Office 365 中的使用者啟用通話方案，您仍需為這些使用者指派**國內通話方案**或**國內與國際通話方案**授權。 請參閱[指派商務用 Skype 和 Microsoft 團隊授權](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。

> [!NOTE]
> 如果您需要取得更多的電話號碼，請[聯絡商務產品支援-系統管理協助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>相關主題
[移轉電話號碼的常見問題](/microsoftteams/transferring-phone-numbers-common-questions)

[通話方案所用的不同類型的電話號碼](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[緊急通話條款及條件](/microsoftteams/emergency-calling-terms-and-conditions)

[商務用 Skype Online：緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
