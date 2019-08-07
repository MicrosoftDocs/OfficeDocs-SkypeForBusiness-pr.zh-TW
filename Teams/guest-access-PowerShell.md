---
title: 使用 PowerShell 控制團隊的來賓存取權
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/25/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: 使用 PowerShell 來允許或封鎖對 Microsoft 團隊中的小組的來賓存取權。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b429d4e2411e697c4e3357ebd7b5fc66ab27376
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2019
ms.locfileid: "36184287"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>使用 PowerShell 控制團隊的來賓存取權
================================================

除了使用 Microsoft 365 系統管理中心以及 Azure Active Directory (Azure AD) 入口網站之外, 您還可以使用 Windows PowerShell 來控制來賓存取。 您可以在 PowerShell 中執行下列動作:
  
- 允許或封鎖來賓對所有團隊和 Office 365 群組的存取權

- 允許將來賓新增至所有團隊和 Office 365 群組

- 允許或封鎖來自特定小組或 Office 365 群組的來賓使用者

如需詳細資訊, 請參閱[管理 Office 365 群組中的來賓存取](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access)中的「使用 PowerShell 控制來賓存取」。
  
您也可以使用 PowerShell 根據其網域來允許或封鎖來賓使用者。 例如, 假設您的企業 (Contoso) 與另一個業務 (Fabrikam) 有合作關係。 您可以將 Fabrikam 新增至您的允許清單, 讓您的使用者可以將這些來賓新增到他們的群組中。 如需詳細資訊, 請參閱[允許/封鎖 Office 365 群組的來賓存取權](https://go.microsoft.com/fwlink/?linkid=854001)。
  
如果您想要封鎖團隊中的來賓, 但仍要允許他們存取 SharePoint 網站, 您可以使用 Azure AD Powershell Cmdlet 停用公司物件上的 AllowGuestsToAccessGroups 參數 (假設已開啟適用于 SharePoint 網站的外部共用).

## <a name="guest-access-vs-external-access"></a>來賓存取與外部存取

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
