---
title: Microsoft Teams顯示器
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
ms.localizationpriority: medium
description: 本文提供Microsoft Teams顯示器支援的概觀和功能。
ms.openlocfilehash: 4b724370ff348f41b8d4c4406a218e1dd1ba0709
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2022
ms.locfileid: "65760865"
---
# <a name="microsoft-teams-displays"></a>Microsoft Teams顯示器

Microsoft Teams顯示器是一種一體專用的Teams裝置類別，配備周遭環境觸控螢幕，以及由Cortana提供的免持聽筒體驗。 本文提供Teams顯示器的概觀，並可協助您規劃、交付和管理貴組織中Teams顯示器。

Teams顯示器將您最愛的Teams功能 &ndash; 整合在單一裝置上，包括聊天、會議、通話、行事曆和檔案 &ndash; 。 透過Teams顯示器，使用者可以使用麥克風、相機和喇叭 (或藍牙耳機) ，以獲得可靠的通話和會議體驗。 Teams顯示器與使用者的Windows電腦整合，帶來可讓跨裝置無縫互動的隨附體驗。

若要深入瞭解，請參[閱Teams顯示器開始](https://support.microsoft.com/office/get-started-with-teams-displays-ff299825-7f13-4528-96c2-1d3437e6d4e6)。

## <a name="features-supported-by-teams-displays"></a>顯示器支援的功能Teams

除了[Teams手機支援的功能](phones-for-teams.md#features-supported-by-teams-phones)之外，下列功能對Teams顯示器是獨一無二的：

- **Teams專用顯示器** 使用者可以存取所有核心Teams功能，包括聊天、會議、通話、團隊和頻道、檔案等。
- **周遭環境體驗** 使用者可以在主要工作裝置上不需切換上下文，就能輕鬆地使用即時且可掃視的顯示器來查看重要活動和通知。 使用者也可以透過設定自訂背景，個人化Teams顯示器。
- **與Cortana** 使用者可以使用語音與Teams顯示器互動，輕鬆加入會議並進行簡報、聽寫Teams聊天的回復、查看行事曆內容等等。
- **在鎖定畫面上保留附注** 來賓可以選擇離開音訊、視訊和文字筆記，而且使用者可以檢查來賓留下的筆記，並查看來賓的停留者。  

## <a name="required-licenses"></a>必要授權

Teams授權可以在Microsoft 365[和Office 365訂閱](/office365/servicedescriptions/teams-service-description)中購買。 若要深入瞭解使用Teams顯示器所需的授權，請參閱Microsoft Teams[語音和視訊通話](https://products.office.com/microsoft-teams/voice-calling)。

如需如何取得Teams的詳細資訊，請參閱[如何?存取Microsoft Teams？](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-teams-displays-using-intune"></a>使用 Intune 部署Teams顯示器

若要深入瞭解如何使用 Intune 部署Teams顯示器，請參閱[部署Teams手機和Teams顯示器](phones-displays-deploy.md)。

## <a name="manage-teams-displays-in-your-organization"></a>管理貴組織中的Teams顯示器

若要管理Teams顯示裝置，請在Microsoft Teams系統管理中心的左側導覽中，移至 **Teams顯示器**。 您可以從這裡變更裝置設定設定檔、管理更新、重新開機裝置、新增和移除裝置標籤等等。 如需詳細資訊，請參閱[在 Teams 中管理您的裝置](device-management.md)。

## <a name="set-up-hot-desking-on-teams-displays"></a>在顯示器上設定快捷桌Teams

熱桌功能可讓貴組織中的人員透過Teams和Outlook，或從裝置本身預先預約臨時工作區。 啟用快捷桌功能時，使用者會使用Microsoft 365認證登入Teams顯示器，以存取其會議、聊天和檔案。 當他們登出時，會從裝置移除他們所有的個人資訊。

若要開始使用，您必須取得Microsoft Teams 會議室標準版授權，並為每個Teams顯示器建立資源帳戶。 請參閱[建立會議室和共用Teams裝置的資源帳戶](../rooms/with-office-365.md)，以建立資源帳戶。

建立資源帳戶之後，您可以建立並指派原則來啟用快捷式桌面功能。 若要深入瞭解，請參閱 [New-CsTeamsIPPhonePolicy](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) 。

> [!IMPORTANT]
> 因為有多個人員會在共用工作區中使用具有快捷桌Teams顯示器，因此條件式存取規則和您環境中的其他身分識別設定，例如多重要素驗證，可能會影響這些裝置並造成登入問題。 如需有關保護共用裝置的指導方針，請參閱[共用Teams Android裝置的驗證最佳做法](authentication-best-practices-for-android-devices.md)。

## <a name="upgrade-teams-phones-to-teams-displays"></a>將Teams手機升級至Teams顯示器

Teams顯示器是Teams手機的進化。 您可以使用Microsoft Teams系統管理中心，將組織中的Teams手機升級至Teams顯示器。 此選項僅適用于支援升級至Teams顯示器的手機。 若要深入瞭解，請參閱[將Teams手機升級至Teams顯示器](upgrade-phones-to-displays.md)。

## <a name="see-also"></a>另請參閱

[Microsoft Teams顯示器簡介](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-displays/ba-p/1505437)

[Teams Marketplace](https://office.com/teamsdevices)

[Teams 的電話](phones-for-teams.md)

[通過 Microsoft Teams 認證的 IP Phone](teams-ip-phones.md)

[將 IP 手機升級至Teams顯示器](upgrade-phones-to-displays.md)

[在 Teams 中Cortana語音協助](../cortana-in-teams.md)