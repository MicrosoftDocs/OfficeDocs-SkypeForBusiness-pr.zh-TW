---
title: 管理使用者對 Microsoft 團隊的存取權
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.reviewer: ritikag
search.appverid: MET150
description: 瞭解如何在每位使用者上啟用或停用使用者層級的存取。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: f571dd461c6c783703159dfd6e9beb343612dd58
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779479"
---
<a name="manage-user-access-to-microsoft-teams"></a>管理使用者對 Microsoft 團隊的存取權
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

在使用者層級，您可以指派或移除 Microsoft 團隊產品授權，在每位使用者上啟用或停用 Microsoft 團隊的存取權。

使用來自團隊系統管理中心管理的訊息原則，以控制可供團隊使用者使用的聊天和通道訊息功能。 您可以針對組織中的人員，使用預設原則或建立一或多個自訂的訊息策略。 若要深入瞭解，請參閱[管理團隊中的訊息傳遞原則](messaging-policies-in-teams.md)。

> [!NOTE]
>Microsoft 建議您針對公司中的所有使用者開啟團隊，讓小組可以針對專案和其他動態方案進行 organically。 即使您決定要試點，仍可將團隊保持為所有使用者使用，但只有目標是與使用者的試驗群組進行通訊。

## <a name="manage-teams-through-the-microsoft-365-admin-center"></a>透過 Microsoft 365 系統管理中心管理團隊

團隊使用者層級授權是透過 Microsoft 365 系統管理中心使用者管理介面直接管理。 系統管理員可以在建立新的使用者帳戶時指派授權給新的使用者，或指派給現有帳戶的使用者。 系統管理員必須具備全域系統管理員或使用者管理管理員的許可權，才能管理 Microsoft 團隊授權。

當您將 E3 或 E5 等授權 SKU 指派給使用者時，系統會自動指派 Microsoft 團隊授權，並為 Microsoft 團隊啟用該使用者。 系統管理員可以對所有 Office 365 服務和授權進行精細的控制，而且可以啟用或停用特定使用者或使用者群組的 Microsoft 團隊授權。

![系統管理中心的 [產品授權] 區段螢幕擷取畫面。](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

團隊使用者授權隨時都可以停用。 授權停用之後，系統就會禁止使用者存取 Microsoft 團隊，而且使用者將無法在 Office 365 應用程式啟動器和首頁中看到團隊。

![顯示 [產品授權] 區段中已選取 [小組] 的螢幕擷取畫面。](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a>透過 PowerShell 管理

> [!IMPORTANT]
> 新的-MsolLicenseOptions 會啟用先前已停用的所有服務，除非您在自訂腳本中明確標示。 例如，如果您想讓 Exchange & Sway 同時停用，同時又停用小組，您必須在腳本中包含這項功能，否則您已識別的使用者就能使用這兩種 Exchange & Sway。 若要使用 GUI 來管理這項功能，請參閱[Office 365 授權報告和管理工具-指派批量移除授權](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)以取得詳細資訊。

透過 PowerShell 啟用和停用團隊作為工作負載授權，就完成了任何其他工作負載。 Microsoft 團隊的服務方案名稱是 TEAMS1。 針對 GCC，服務方案名稱是 TEAMS_GOV。 針對 GCC 高版，服務方案名稱是 TEAMS_GCCHIGH。 如果是 DoD，服務方案名稱是 TEAMS_DOD （請參閱[使用 Office 365 PowerShell 停用服務的存取權](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell)，以取得詳細資訊。）

**範例：** 以下只是一個快速範例，說明如何針對特定授權類型的每個人停用團隊。 您必須先執行此動作，然後針對需要試驗的使用者逐一啟用此動作。

若要顯示貴組織內擁有的訂閱類型，請使用下列命令：

      Get-MsolAccountSku

填入包括貴組織名稱和學校方案的方案名稱（例如 ContosoSchool： ENTERPRISEPACK_STUDENT），然後執行下列命令：

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
若要針對所有擁有您命名方案之有效授權的使用者停用團隊，請執行下列命令：

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![代表決策點的圖示](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |決策點         |<ul><li>貴組織在整個組織中要加入哪些小組的方案？  （試驗或開啟）</li></ul>         |
|![代表後續步驟的圖示](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |後續步驟         |<ul><li>如果您是透過關閉的試運行進行加入，請決定您是否要透過授權或目標通訊來執行此操作。</li><li>根據決定，請採取步驟以確保只有獲允許存取團隊的試驗使用者（視需要）。</li><li>針對將（或將沒有）存取團隊的使用者記錄指導方針。</li></ul>         |

## <a name="manage-teams-at-the-office-365-organization-level"></a>在 Office 365 組織層級管理團隊
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

