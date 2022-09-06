---
title: Microsoft Teams 顯示器
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
- Teams_ITAdmin_Devices
search.appverid: MET150
ms.localizationpriority: medium
description: 本文提供 Microsoft Teams 顯示器所支援的概觀和功能。
ms.openlocfilehash: 8b06078633dd8c7ee43c2ee98ad1f3e4751d3a51
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606022"
---
# <a name="microsoft-teams-displays"></a>Microsoft Teams 顯示器

Microsoft Teams 顯示器是一種一對一專用的 Teams 裝置類別，可提供周遭環境觸控螢幕，以及由 Cortana 提供的免持聽筒體驗。 本文提供 Teams 顯示器的概觀，並可協助您規劃、交付和管理貴組織中的 Teams 顯示器。

Teams 顯示器將您最愛的 Teams 功能 &ndash; 聊天、會議、通話、行事曆和檔案 &ndash; 整合到單一裝置中。 透過 Teams 顯示器，使用者可以使用麥克風、相機和喇叭 (或藍牙耳機) ，以獲得可靠的通話和會議體驗。 Teams 顯示器與使用者的 Windows 電腦整合，為您帶來可順暢跨裝置互動的隨附體驗。

若要深入瞭解，請參閱 [開始使用 Teams 顯示器](https://support.microsoft.com/office/get-started-with-teams-displays-ff299825-7f13-4528-96c2-1d3437e6d4e6)。

## <a name="features-supported-by-teams-displays"></a>Teams 顯示器支援的功能

除了 [Teams 手機支援的功能](phones-for-teams.md#features-supported-by-teams-phones)之外，Teams 顯示器也具有下列唯一功能：

- **Teams 專用顯示器** 使用者可以存取所有核心 Teams 功能，包括聊天、會議、通話、團隊和頻道、檔案等。
- **周遭環境體驗** 使用者可以在主要工作裝置上不需切換上下文，就能輕鬆地使用即時且可掃視的顯示器來查看重要活動和通知。 使用者也可以透過設定自訂背景，個人化 Teams 顯示器。
- **使用 Cortana 免持聽筒** 使用者可以使用語音與 Teams 顯示器互動，輕鬆加入會議並進行簡報、聽寫 Teams 聊天的回復、查看行事曆上的內容等等。
- **在鎖定畫面上保留附注** 來賓可以選擇離開音訊、視訊和文字筆記，而且使用者可以檢查來賓留下的筆記，並查看來賓的停留者。  

## <a name="required-licenses"></a>必要授權

您可以在[Microsoft 365 和 Office 365 訂閱](/office365/servicedescriptions/teams-service-description)中購買 Teams 授權。 若要深入瞭解使用 Teams 顯示器所需的授權，請參閱 [使用 Microsoft Teams 進行語音和視訊通話](https://products.office.com/microsoft-teams/voice-calling)。

如需如何取得 Teams 的詳細資訊，請參[閱如何?取得 Microsoft Teams 的存取權？](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-teams-displays-using-intune"></a>使用 Intune 部署 Teams 顯示器

若要深入瞭解如何使用 Intune 部署 Teams 顯示器，請參閱[部署 Teams 手機和 Teams 顯示器](phones-displays-deploy.md)。

## <a name="manage-teams-displays-in-your-organization"></a>管理組織中的 Teams 顯示器

若要管理您的 Teams 顯示裝置，請在 Microsoft Teams 系統管理中心的左側導覽中，移至 **Teams 顯示器**。 您可以從這裡變更裝置設定設定檔、管理更新、重新開機裝置、新增和移除裝置標籤等等。 如需詳細資訊，請參閱 [在 Teams 中管理您的裝置](device-management.md)。

## <a name="set-up-hot-desking-on-teams-displays"></a>在 Teams 顯示器上設定快捷方式

熱門桌面功能可讓貴組織中的人員透過 Teams 和 Outlook，或從裝置本身預先預約臨時工作區。 啟用快捷式桌面功能時，使用者使用其 Microsoft 365 認證登入 Teams 顯示器，以存取其會議、聊天和檔案。 當他們登出時，會從裝置移除他們所有的個人資訊。

若要開始使用，您必須取得[Microsoft Teams 會議室授權](../rooms/rooms-licensing.md)，並為每個 Teams 顯示器建立資源帳戶。 請參閱 [建立會議室和共用 Teams 裝置的資源帳戶](../rooms/with-office-365.md) ，以建立資源帳戶。

建立資源帳戶之後，您可以建立並指派原則來啟用快捷式桌面功能。 若要深入瞭解，請參閱 [New-CsTeamsIPPhonePolicy](/powershell/module/skype/new-csteamsipphonepolicy) 。

> [!IMPORTANT]
> 因為 Teams 配備快速鍵的顯示器會被多人用於共用工作區，因此條件式存取規則和您環境中的其他身分識別設定，例如多重要素驗證，可能會影響這些裝置並造成登入問題。 如需有關保護共用裝置的指導方針，請參閱 [共用 Teams Android 裝置的驗證最佳做法](authentication-best-practices-for-android-devices.md)。

## <a name="upgrade-teams-phones-to-teams-displays"></a>將 Teams 手機升級至 Teams 顯示器

Teams 顯示器是 Teams 手機的演進。 您可以使用 Microsoft Teams 系統管理中心，將貴組織中的 Teams 手機升級至 Teams 顯示器。 此選項僅適用于支援升級至 Teams 顯示器的手機。 若要深入瞭解，請參閱 [將 Teams 手機升級至 Teams 顯示器](upgrade-phones-to-displays.md)。

## <a name="see-also"></a>另請參閱

[Microsoft Teams 顯示器簡介](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-displays/ba-p/1505437)

[Teams 市集](https://office.com/teamsdevices)

[Teams 的電話](phones-for-teams.md)

[通過 Microsoft Teams 認證的 IP 手機](teams-ip-phones.md)

[將 IP 手機升級至 Teams 顯示器](upgrade-phones-to-displays.md)

[Teams 中的 Cortana 語音協助](../cortana-in-teams.md)