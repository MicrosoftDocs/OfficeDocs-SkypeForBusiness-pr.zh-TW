---
title: Microsoft Teams顯示
ms.author: czawideh
author: cazawideh
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
description: 本文提供螢幕顯示功能Microsoft Teams概觀。
ms.openlocfilehash: 8c8004edd12042ca27e77e545f23b8770f8d1899
ms.sourcegitcommit: e9b0a274fdfee3d5bc8211cb099155546b281fe0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2022
ms.locfileid: "62926326"
---
# <a name="microsoft-teams-displays"></a>Microsoft Teams顯示

Microsoft Teams顯示器是一種一體式專用Teams裝置，具有環境觸控螢幕和由螢幕Cortana。 本文提供顯示Teams概觀，並可協助規劃、傳遞及管理Teams顯示內容。

Teams顯示器會將您最愛的Teams聊天 &ndash; &ndash; 、會議、通話、日曆和檔案彙集到單一裝置。 有了Teams，使用者可以使用麥克風、相機和喇叭 (耳機藍牙耳機) 通話和會議體驗。 Teams顯示器會與使用者Windows電腦整合，以帶來可順暢跨裝置互動的配套體驗。

若要深入瞭解，請查看開始使用[Teams顯示](https://support.microsoft.com/office/get-started-with-teams-displays-ff299825-7f13-4528-96c2-1d3437e6d4e6)。

## <a name="features-supported-by-teams-displays"></a>顯示由 Teams支援的功能

除了手機[支援的功能](phones-for-teams.md#features-supported-by-teams-phones)Teams，下列功能在顯示時Teams獨一無二：

- **適用于使用者的專用Teams** 使用者可以存取所有核心Teams功能，包括聊天、會議、通話、團隊和頻道、檔案等。
- **環境體驗** 使用者可以在主要工作裝置上輕鬆使用隨時開啟且易於流覽的顯示器，隨時查看重要活動和通知，而不需要切換內容。 使用者也可以透過設定Teams個人化顯示內容。
- 使用 Cortana，使用者可以使用語音與 Teams 顯示器互動，輕鬆加入會議並出席會議、聽寫 Teams 聊天的回復、查看日曆上有什麼內容等等。
- **在鎖定畫面上保留記事** 來賓可以選擇離開音訊、視視和文字筆記，而使用者可以檢查來賓留下的筆記，並查看誰被誰停過。  

## <a name="required-licenses"></a>必要的授權

Teams訂閱和訂閱的一Microsoft 365購買[Office 365授權](/office365/servicedescriptions/teams-service-description)。 若要深入瞭解使用顯示器所需的授權[Teams，請參閱](https://products.office.com/microsoft-teams/voice-calling)使用語音和視Microsoft Teams。

若要瞭解如何取得Teams，請參閱如何[存取Microsoft Teams？](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-teams-displays-using-intune"></a>使用 intune Teams顯示部署

若要深入瞭解如何使用 Intune Teams顯示，請參閱部署Teams[和Teams顯示](phones-displays-deploy.md)。

## <a name="manage-teams-displays-in-your-organization"></a>管理Teams顯示

若要管理您的 Teams顯示裝置，請前往系統管理中心左側導Microsoft Teams，前往 Teams **顯示**。 您可以在這裡變更裝置組調設定檔、管理更新、重新開機裝置、新增和移除裝置標記等等。 詳細資訊，請參閱在 Teams[中管理您的Teams](device-management.md)。

## <a name="set-up-hot-desking-on-teams-displays"></a>在顯示器上設定Teams桌面

使用桌面服務，貴組織人員可以透過Teams或裝置Outlook預先預約臨時工作區。 啟用熱桌面時，使用者Teams會以Microsoft 365的認證來存取其會議、聊天和檔案。 當他們登出時，他們的所有個人資訊會從裝置中移除。

若要開始使用，您必須取得Microsoft Teams 會議室標準版授權，並為每個顯示專案建立Teams帳戶。 請參閱[使用 Microsoft Teams 會議室 部署Office 365](../rooms/with-office-365.md)以建立資源帳戶。

建立資源帳戶之後，您可以建立並指派策略以啟用桌面桌面。 如需 [深入瞭解，請參閱 New-CsTeamsIPPhonePolicy](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) 。

> [!IMPORTANT]
> 由於Teams桌面的顯示器會由多人在共用工作區中使用，因此條件式 Access 規則及您環境中的其他身分識別組組 ，例如多重要素驗證，可能會影響這些裝置，並造成登錄問題。 有關保護共用裝置之指南，請參閱 Android 裝置共用之[Teams最佳做法](authentication-best-practices-for-android-devices.md)。

## <a name="upgrade-teams-phones-to-teams-displays"></a>將Teams手機升級至Teams顯示

Teams顯示的是手機Teams演進。 您可以使用系統管理Teams，將組織中Teams手機升級Microsoft Teams顯示。 此選項僅適用于支援升級至Teams顯示。 若要深入瞭解，請參閱將[手機Teams至Teams顯示](upgrade-phones-to-displays.md)。

## <a name="see-also"></a>另請參閱

[顯示Microsoft Teams介紹](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-displays/ba-p/1505437)

[Teams市集](https://office.com/teamsdevices)

[Teams 的電話](phones-for-teams.md)

[IP 電話已Microsoft Teams](teams-ip-phones.md)

[將 IP 電話升級Teams顯示](upgrade-phones-to-displays.md)

[Cortana語音協助Teams](../cortana-in-teams.md)