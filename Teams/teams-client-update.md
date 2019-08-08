---
title: 團隊更新
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/13/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
description: 瞭解小組桌面用戶端的更新方式。
appliesto:
- Microsoft Teams
ms.openlocfilehash: e0fe542c6df89946ad73f14cf9104f973e292aa3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243839"
---
# <a name="teams-update-process"></a>小組更新流程

團隊 web app 會每週更新一次。

小組的桌面用戶端更新會在經過我們的技術採納計畫 (攻絲) 嚴格內部測試和驗證之後, 每兩周發行一次。 這通常會在星期二進行。 如果需要重要更新, 小組會略過此排程, 並在更新推出後立即發行更新。

桌面用戶端會自動更新。 團隊會在幕後每隔幾小時檢查更新、下載更新, 然後等到電腦處於空閒狀態, 然後才能自行安裝更新。

使用者也可以按一下應用程式右上方的 [檢查**設定檔**] 下拉式功能表上的 [**檢查更新**], 手動下載更新。 如果有可用的更新, 系統會在電腦空閒時下載並自動安裝。

使用者必須登入, 才能下載更新。 

從2019年7月9日開始, 團隊用戶端更新在更新期間使用明顯較低的網路頻寬。 此功能預設為開啟, 且不需要系統管理員或使用者執行任何動作。


## <a name="what-about-updates-to-office-365-proplus"></a>Office 365 專業增強版的更新內容是什麼？

依[使用 office 365 專業增強版部署 Microsoft 團隊](https://docs.microsoft.com/DeployOffice/teams-install)中所述, 預設會在新安裝的 Office 365 專業增強版中安裝團隊。 

團隊會依照上面所述的更新程式, 而不是其他辦公室應用程式 (例如 Word 和 Excel) 的更新程式。 若要深入瞭解, 請參閱[Office 365 專業增強版更新通道的概覽](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)

## <a name="what-about-updates-to-teams-on-vdi"></a>VDI 上的小組更新為何？

虛擬桌面基礎結構 (VDI) 上的團隊用戶端不會自動更新非 VDI 團隊用戶端的方式。 您必須安裝新的 MSI 來更新 VM 影像, 如在[VDI 上安裝小組](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi)中所述。 您必須卸載目前的版本, 才能更新為較新的版本。

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>管理員是否可以部署更新, 而不是團隊自動更新？

團隊不會給予管理員透過任何傳遞機制部署更新的功能。
