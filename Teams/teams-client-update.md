---
title: Teams更新
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
description: 在本文中，您將瞭解更新桌面用戶端Microsoft Teams程式。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 004c615d2b624f4e5942562e6abfed6e1aebf7cd
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717894"
---
# <a name="teams-update-process"></a>Teams更新程式

Teams Web App 每週更新一次。

Teams透過我們的技術採用計畫與 TAP (，每兩周發佈一次桌面用戶端) 。 更新通常會在星期二進行。 如果需要重大更新，Teams會忽略此排程，並儘快發佈更新。

桌面用戶端會自動更新本身。 Teams每隔幾個小時在幕後檢查更新、下載更新，然後等待電腦閒置，再以無提示方式安裝更新。

使用者也可以選取應用程式右上方的設定檔下拉式功能表上的檢查更新，以手動下載更新。 如果有可用的更新，系統就會在電腦閒置時下載並以無提示方式安裝更新。

使用者必須登錄，以下載更新。

自 2019 年 7 月 31 日起，Teams更新期間，用戶端更新會使用較低的網路頻寬。 此更新預設為開啟，且不需要系統管理員或使用者執行任何動作。

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>更新至Microsoft 365 Apps 企業版？

Teams預設會安裝新的 Microsoft 365 Apps 企業版 安裝，如使用 Microsoft Teams[部署 Microsoft 365 Apps 企業版。](/DeployOffice/teams-install)

Teams遵循上述其更新程式。 Teams不會遵循其他辦公室應用程式的更新程式，例如 Word 和 Excel。 若要深入瞭解[，請參閱更新](/DeployOffice/overview-of-update-channels-for-office-365-proplus)通道概觀Microsoft 365 Apps 企業版

## <a name="what-about-updates-to-teams-on-vdi"></a>在 VDI 上Teams更新呢？


Teams虛擬桌面基礎結構 (VDI) 上的用戶端不會以非 VDI 用戶端Teams的方式自動更新。 您必須安裝新的 MSI 以更新 VM 映射，如在[VDI](teams-for-vdi.md)上安裝Teams所述。 您必須卸載目前的版本，以更新至較新版本。

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>系統管理員可以部署更新，而不是Teams自動更新嗎？

Teams無法讓系統管理員透過任何傳遞機制部署更新。

## <a name="servicing-agreement"></a>維護協定

做為新式線上服務，Teams用戶端每兩周自動更新一次。 由於Teams受新式生命週期政策所規範，因此使用者預期會維持在桌面用戶端的最新版本。 自動更新可確保使用者擁有最新的功能、增強功能、安全性和服務可靠性。

若要識別桌面用戶端何時過期，如果使用者的目前版本介於 1 到 3 個月之間，以及是否有可用的新版本，則會顯示應用程式內通知。 此 App 內訊息可鼓勵使用者更新至最新版本Teams或在必要時，與 IT 系統管理員聯繫以執行此操作。 超過Teams桌面用戶端的使用者會看到封鎖頁面，提供目前更新、連至 IT 系統管理員或繼續Teams網頁版的選項。

Teams雲端上的桌面用戶端目前在此服務協定有例外，直到進一步通知為止。

有關新版本發行的資訊，請查看 [訊息中心](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter)或前往說明  >  **用戶端** 的新增功能。
