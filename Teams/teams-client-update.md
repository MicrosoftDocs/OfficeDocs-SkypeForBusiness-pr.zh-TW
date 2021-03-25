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
description: 在本文中，您將瞭解更新 Microsoft Teams 桌面用戶端背後的程式。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68e26325f4efcc5ffd7731b73e397f1f96579dd5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119242"
---
# <a name="teams-update-process"></a>Teams 更新程式

Teams Web App 每週更新一次。

透過我們的技術採用計畫與 TAP (，每兩周發佈一次 Teams 桌面) 。 更新通常會在星期二進行。 如果需要重大更新，Teams 會忽略此排程，並儘快發佈更新。

桌面用戶端會自動更新本身。 Teams 會每隔幾個小時在幕後檢查更新、下載更新，然後等待電腦閒置，再以無提示方式安裝更新。

使用者也可以選取應用程式右上方的設定檔下拉式功能表上的檢查更新，以手動下載更新。 如果有可用的更新，系統就會在電腦閒置時下載並以無提示方式安裝更新。

使用者必須登錄，以下載更新。

自 2019 年 7 月 31 日起，Teams 用戶端更新在更新期間會使用較低的網路頻寬。 此更新預設為開啟，且不需要系統管理員或使用者執行任何動作。

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>適用于企業的 Microsoft 365 App 更新呢？

根據預設，Teams 會安裝新的 Microsoft 365 企業版應用程式安裝，如使用 [Microsoft 365](/DeployOffice/teams-install)企業版 App 部署 Microsoft Teams 中所述。

如上所述，Teams 會遵循自己的更新程式。 Teams 不會遵循其他辦公室應用程式的更新程式，例如 Word 和 Excel。 若要深入瞭解，請參閱 [企業版 Microsoft 365 應用程式更新通道概觀](/DeployOffice/overview-of-update-channels-for-office-365-proplus)

## <a name="what-about-updates-to-teams-on-vdi"></a>VDI 上的 Teams 更新呢？


虛擬桌面基礎結構上的 Teams (VDI) 不會以非 VDI Teams 用戶端的方式自動更新。 您必須按照在 VDI 上安裝 Teams 的指示，安裝新的 [MSI](teams-for-vdi.md)來更新 VM 映射。 您必須卸載目前的版本，以更新至較新版本。

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>系統管理員可以部署更新，而不是 Teams 自動更新嗎？

Teams 不會提供系統管理員透過任何傳遞機制部署更新的能力。

## <a name="servicing-agreement"></a>維護協定

Teams 用戶端是一種新式線上服務，每兩周自動更新一次。 由於 Teams 受新式生命週期策略所規範，因此使用者預期會維持在桌面用戶端的最新版本。 自動更新可確保使用者擁有最新的功能、增強功能、安全性和服務可靠性。

若要識別桌面用戶端何時過期，如果使用者的目前版本介於 1 到 3 個月之間，以及是否有可用的新版本，則會顯示應用程式內通知。 此 App 內訊息可鼓勵使用者更新至最新版本的 Teams，或在必要時與 IT 系統管理員聯繫以執行這項操作。 超過三個月的 Teams 桌面用戶端使用者會看到封鎖頁面，提供現在更新、連至 IT 系統管理員或繼續使用 Teams 網頁版的選項。

第一次安裝及/或第一次執行 Teams 時超過 3 個月的桌面用戶端版本，在遇到上述維護資訊之前，有 28 天的寬限期。 在此期間，自動更新程式會更新 Teams 用戶端。 如果未更新，使用者會看到應用程式內通知，鼓勵他們手動更新至最新版本的 Teams。 系統可能會提示使用者與 IT 系統管理員聯繫以進行更新。 這包括使用 Teams 桌面用戶端作為 Microsoft 365 應用程式企業套件一部分的使用者。

在進一步通知之前，政府雲端上的 Teams 桌面用戶端目前有此服務協定的例外。

有關新版本發行的資訊，請查看 [訊息中心](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter)或前往說明  >  **用戶端** 的新增功能。
