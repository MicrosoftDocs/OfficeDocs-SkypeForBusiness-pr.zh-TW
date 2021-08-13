---
title: Teams 更新
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: annaray
search.appverid: MET150
f1.keywords:
- NOCSH
description: 在本文中，您將了解更新 Microsoft Teams 桌面用戶端背後的程序。
localization_priority: Priority
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 96077e5b50dff12f29f6e1ccf903cd0f7de96352dacf0d8b3c2cc7406750737e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321135"
---
# <a name="teams-update-process"></a>Teams 更新程序

Teams Web 應用程式會每週更新。

透過我們的技術採用計畫 (TAP)，Teams 桌面用戶端更新會在嚴格的內部測試和驗證之後每兩週發行一次。 更新通常會在星期二進行。 如果需要重大更新，Teams 會略過此排程，並在更新一推出就立即發行更新。

桌面用戶端會自動自行更新。Teams 會每隔數小時在幕後檢查更新、下載更新，然後等待電腦閒置，然後以無訊息方式安裝更新。

使用者也可以選取應用程式右上方 **[設定檔]** 下拉式功能表上的 **[檢查更新]**，以手動下載更新。 如果有可用的更新，當電腦閒置時，將會下載並以無訊息方式安裝更新。

使用者必須已登入才能下載更新。

自 2019 年 7 月 31 日起，Teams 用戶端更新在更新期間使用較低的網路頻寬。 此更新預設為開啟，不需要系統管理員或使用者執行任何動作。

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>如何更新 Microsoft 365 Apps 企業版？

Teams 預設會隨著 Microsoft 365 Apps 企業版的新安裝一起安裝，請參閱[使用 Microsoft 365 Apps 企業版部署 Microsoft Teams](/DeployOffice/teams-install) 中的說明。

如上述所述，Teams 會遵循自己的更新程序。 Teams 不會遵循其他 Office 應用程式的更新程序，例如 Word 和 Excel。 若要深入了解，請參閱 [Microsoft 365 Apps 企業版更新通道的概觀](/DeployOffice/overview-of-update-channels-for-office-365-proplus)。

## <a name="what-about-updates-to-teams-on-vdi"></a>如何更新 VDI 上的 Teams ？


虛擬桌面基礎結構 (VDI) 上的 Teams 用戶端不會以非 VDI Teams 用戶端的方式自動更新。 您必須安裝新的 MSI 以更新 VM 映像，請參閱[在 VDI 中安裝 Teams](teams-for-vdi.md) 中的說明。 您必須解除安裝目前的版本，以更新至較新的版本。

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>系統管理員可以部署更新，而不是 Teams 自動更新嗎？

Teams 不會提供系統管理員透過任何傳遞機制部署更新的能力。

## <a name="servicing-agreement"></a>維護協議

Teams 用戶端是新式線上服務，每兩週自動更新一次。 由於 Teams 受到新式生命週期原則的規範，因此使用者應該會維持在最新版的桌面用戶端上。 自動更新可確保使用者擁有最新的功能、效能增強功能、安全性和服務可靠性。

若要識別桌面用戶端何時過期，如果使用者的目前版本介於 1 到 3 個月之間，以及如果有可用的新版本，則會顯示應用程式內警示。 此應用程式內訊息會鼓勵使用者更新至最新版的 Teams，或在必要時與 IT 系統管理員連絡以執行這項操作。 在 Teams 桌面用戶端上超過三個月的使用者會看到封鎖頁面，該頁面提供現在更新、連絡 IT 系統管理員或繼續使用 Teams 網頁版的選項。

在進一步通知之前，政府雲端上的 Teams 桌面用戶端目前對此服務協定有例外。

有關新版本的資訊，請查看 [訊息中心](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter)或前往用戶端中的 **[說明]** > **[新增功能]**。
