---
title: 團隊更新
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
description: 瞭解小組桌面用戶端的更新方式。
appliesto:
- Microsoft Teams
ms.openlocfilehash: ace50cc0f9c59375c5a182cf18559b0a449db109
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570253"
---
# <a name="teams-update-process"></a>小組更新流程

團隊 web app 會每週更新一次。

小組的桌面用戶端更新會在經過我們的技術採納計畫（攻絲）嚴格內部測試和驗證之後，每兩周發行一次。 這通常會在星期二進行。 如果需要重要更新，小組會略過此排程，並在更新推出後立即發行更新。

桌面用戶端會自動更新。 團隊會在幕後每隔幾小時檢查更新、下載更新，然後等到電腦處於空閒狀態，然後才能自行安裝更新。

使用者也可以按一下應用程式右上方的 [檢查**設定檔**] 下拉式功能表上的 [**檢查更新**]，手動下載更新。 如果有可用的更新，系統會在電腦空閒時下載並自動安裝。

使用者必須登入，才能下載更新。 

從2019年7月31日起，團隊用戶端更新在更新期間使用明顯較低的網路頻寬。 此功能預設為開啟，且不需要系統管理員或使用者執行任何動作。

## <a name="what-about-updates-to-office-365-proplus"></a>Office 365 專業增強版的更新內容是什麼？

依[使用 office 365 專業增強版部署 Microsoft 團隊](https://docs.microsoft.com/DeployOffice/teams-install)中所述，預設會在新安裝的 Office 365 專業增強版中安裝團隊。 

團隊會依照上面所述的更新程式，而不是其他辦公室應用程式（例如 Word 和 Excel）的更新程式。 若要深入瞭解，請參閱[Office 365 專業增強版更新通道的概覽](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)

## <a name="what-about-updates-to-teams-on-vdi"></a>VDI 上的小組更新為何？

虛擬桌面基礎結構（VDI）上的團隊用戶端不會自動更新非 VDI 團隊用戶端的方式。 您必須安裝新的 MSI 來更新 VM 影像，如在[VDI 上安裝小組](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi)中所述。 您必須卸載目前的版本，才能更新為較新的版本。

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>管理員是否可以部署更新，而不是團隊自動更新？

團隊不會給予管理員透過任何傳遞機制部署更新的功能。

## <a name="servicing-agreement"></a>服務合約

作為現代的線上服務，小組用戶端會每兩周自動更新一次。 由於團隊是由現代的生命週期原則所管理，因此，使用者可能會保持最新版本的桌面用戶端。 這可確保使用者擁有最新的功能、效能增強、安全性和服務可靠性。

若要在桌面用戶端過期時開始協助識別，如果使用者的目前版本在一到三個月之間，且有可用的新版本，就會顯示應用程式內警示。 此應用程式內訊息鼓勵使用者更新到最新版本的小組，或視需要向 IT 系統管理員進行更新。 在超過三個月之前的小組桌面用戶端上，系統會顯示封鎖頁面，提供立即更新、與 IT 管理員聯繫，或繼續在網路上的小組中的選項。

在第一次安裝和/或第一次執行團隊後的桌面用戶端版本超過三個月，在遇到上述服務資訊之前，會有28天的寬限期。 在此期間，自動更新程式將會更新團隊用戶端。 如果未更新，使用者就會看到應用程式內的警示，鼓勵他們手動更新為最新版本的團隊，或視需要向 IT 系統管理員確認。 這包括使用小組桌面用戶端的使用者做為 Office 365 專業增強版套件的一部分。

政府群的小組桌面用戶端目前有此服務協定的例外狀況，直到進一步通知。

如需新版版本的詳細資訊，請參閱[訊息中心](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter)或移至**協助** > 用戶端**的新增功能**。
