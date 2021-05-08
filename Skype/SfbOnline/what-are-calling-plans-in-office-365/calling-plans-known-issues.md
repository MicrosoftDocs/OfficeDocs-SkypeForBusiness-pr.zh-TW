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
description: 瞭解 PSTN 通話的通話方案已知問題，以及您可以採取哪些處理方式。
ms.openlocfilehash: 9c660ee3b173f104e26816460db45c5bcf400837
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238019"
---
# <a name="calling-plans-known-issues"></a>通話方案已知問題

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

通話方案是線上通話的商務用 Skype功能。 以下是目前正在追蹤並積極調查的目前問題。 當功能在未來建立中更新時，這些衝突可能會解決。
  
## <a name="calling-plans-known-issues"></a>通話方案已知問題

|**已知問題**|**註解**|
|:-----|:-----|
|從 Tech Preview 授權轉換為通話方案生產授權不會自動更新授權。  <br/> |首先購買您的新授權，以便準備好指派給使用者。 從使用者 (技術預覽版) 促銷，然後立即指派新的國內通話方案及/或國內及國際通話方案授權給使用者。  <br/> 如果您要移除並新增多個使用者授權，從使用 Windows PowerShell 的所有使用者移除授權，然後立即指派授權給所有同時使用 Windows PowerShell 的使用者，這Windows PowerShell。 這麼做可確保處理大量使用者授權指派時，服務不會中斷。 有關 PowerShell 腳本範例，請參閱指派[商務用 Skype及Microsoft Teams授權](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。  <br/> **注意：** 如果您為混合式使用者使用內部部署 PSTN 連接，則只需要指派 **電話系統授權。** 您 **也不應該** 指派語音通話方案。 不過，如果您在 Microsoft 365 或 Office 365 中為 Microsoft 365 或 Office 365 中的使用者啟用通話方案，您仍然需要為這些使用者指派國內通話方案或國內和國際通話方案授權。  請參閱[指派商務用 Skype和Microsoft Teams授權](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。

> [!NOTE]
> 如果您需要取得更多電話號碼，請聯絡商務產品支援人員 [- 系統管理協助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>相關主題
[移轉電話號碼的常見問題](/microsoftteams/transferring-phone-numbers-common-questions)

[用於通話方案的各種電話號碼](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[緊急通話條款及條件](/microsoftteams/emergency-calling-terms-and-conditions)

[商務用 Skype線上：緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
