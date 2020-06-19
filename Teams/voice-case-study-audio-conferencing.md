---
title: 團隊語音 Contoso 案例研究
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 多國企業的小組語音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: f58f3518202fd836ff962374e8f3b3a00ab71817
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785982"
---
# <a name="contoso-case-study-audio-conferencing"></a>Contoso 案例研究：音訊會議

若要瞭解音訊會議的 &mdash; 內容、其成本、可用性，以及它如何運作， &mdash; Contoso[在 Office 365 中審查音訊會議](deploy-audio-conferencing-teams-landing-page.md)。 

## <a name="overview"></a>概觀 

對於音訊會議，Contoso 在組織內以及外部使用的電話號碼。 由於 Contoso 想要盡可能保留這些數位，因此他們已複習將專用和共用電話號碼指派給音訊會議橋接器的相關資訊。 

根據其研究，Contoso 進行下列決策： 

- 只有定期託管音訊會議呼叫的一部分人口，才會收到音訊會議授權。 

- Contoso 會使用專用的電話號碼，並將其現有的號碼與音訊會議搭配使用。   

因為 Contoso 使用者使用的是商務用 Skype，且所有使用者的信箱都在線上，所以許多使用者已安排現有的會議。 Contoso 已[使用會議遷移服務（MMS）](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)進行閱讀，以瞭解在將使用者變更為 TeamsOnly 模式時，會自動為 Contoso 更新現有的會議。  


## <a name="configuration"></a>Configuration

與音訊會議相關聯的電話號碼稱為電話系統中的服務號碼。 

- 針對使用通話方案的位置，若要將其電話載波中的現有電話號碼移植至 Office 365，Contoso 請按照[取得服務電話號碼](getting-service-phone-numbers.md)中的步驟進行。

- 若要將音訊會議授權指派給技術試驗中的最終使用者，Contoso 管理員請按照[管理貴組織的音訊會議設定](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)中的步驟操作。 

- 針對業務試驗與遷移，Contoso 使用以群組為基礎的授權，請按照在[Azure Active Directory 中的群組成員資格指派授權給使用者](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)。  

 

 