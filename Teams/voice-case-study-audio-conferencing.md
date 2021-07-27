---
title: Teams語音 Contoso 案例研究：音訊會議
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
description: Teams多國公司的語音案例研究：音訊會議
appliesto:
- Microsoft Teams
ms.openlocfilehash: e9f4dd4781a8ea6a60528aaa3e4b208efc1a8f5e
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587302"
---
# <a name="contoso-case-study-audio-conferencing"></a>Contoso 案例研究：音訊會議

若要瞭解音訊會議是什麼、費用、可用性，以及音訊會議運作方式，Contoso 在 Office 365 &mdash; &mdash; 中[已Office 365。](deploy-audio-conferencing-teams-landing-page.md) 

## <a name="overview"></a>概觀 

對於音訊會議，Contoso 會使用組織中以及外部都已知的電話號碼。 由於 Contoso 想要盡可能維護這些號碼，因此他們審閱了將專用和共用電話號碼指派給音訊會議橋接器的資訊。 

Contoso 根據他們的研究做出下列決定： 

- 只有定期主持音訊會議通話的一部分人口會收到音訊會議授權。 

- Contoso 會使用專用電話號碼，並移植現有的號碼，以用於音訊會議。   

由於 Contoso 使用者使用的是商務用 Skype且所有使用者的信箱都位於線上，因此許多使用者已排程現有的會議。 Contoso 閱讀使用會議移 ([MMS) ， ](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json) 以瞭解當將使用者變更為 TeamsOnly 模式時，系統會自動更新 Contoso 的現有會議。  


## <a name="configuration"></a>配置

電話與音訊會議相關聯的號碼，稱為電話系統。 

- 對於使用通話方案的位置，若要將現有的電話號碼從電話電信Office 365，Contoso 會遵循取得服務電話號碼[中的步驟](getting-service-phone-numbers.md)。

- 若要在技術試驗中指派音訊會議授權給使用者，Contoso 系統管理員遵循管理貴組織的音訊會議設定 [中的步驟](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)。 

- 針對商務試驗和移移，Contoso 使用群組式授權，方法如下：在 Azure Active Directory 中按照群組成員資格[指派授權給使用者](/azure/active-directory/users-groups-roles/licensing-groups-assign)。  

 

