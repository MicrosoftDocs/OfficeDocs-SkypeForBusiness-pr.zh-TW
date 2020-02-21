---
title: 在 Microsoft 團隊中為您的組織管理倒班應用程式
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何針對貴組織中的第一線員工工作人員，在小組中設定和管理倒班 app。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 134ff131307034381b97643a2bf9a3dd7fc87a7d
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161856"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>在 Microsoft 團隊中為您的組織管理倒班應用程式

> [!IMPORTANT]
> 2019年12月31日生效，Microsoft StaffHub 將停用。 我們正在將 StaffHub 功能組建至 Microsoft 團隊。 今天，小組包含針對排程管理的倒班應用程式，而其他功能則會隨著時間推移而推出。 StaffHub 將會停止針對2019年12月31日的所有使用者使用。 任何試圖開啟 StaffHub 的人，都會顯示一則訊息，讓他們下載小組。 若要深入瞭解，請參閱[Microsoft StaffHub 停用](microsoft-staffhub-to-be-retired.md)。  

## <a name="overview-of-shifts"></a>班次的概覽

Microsoft 團隊中的 [倒班] 應用程式會讓第一線員工工作人員保持連線並同步處理。它會先建立行動裝置，以快速且有效地管理和溝通小組的時間。 [倒班] 讓第一線員工工作者及其主管使用行動裝置管理排程，並保持聯繫。 

- 管理員建立、更新及管理團隊的倒班排程。 他們可以將訊息傳送給一個人（「在地面有溢出）」或整個小組（「地區 GM 已在20分鐘內抵達」）。 他們也可以傳送原則檔、新聞佈告及影片。 
- 員工要查看他們的後續班次，可以查看當天排程的人員、要求交換或提供倒班，以及要求下班時間。 

我們必須知道，倒班目前不支援來賓使用者。 這表示當您在小組中開啟來賓存取功能時，小組中的來賓不能加入或使用倒班排程。 

## <a name="availability-of-shifts"></a>倒班的可用性

在可使用團隊的所有企業 Sku 中，都提供倒班。

## <a name="location-of-shifts-data"></a>倒班資料的位置

倒班資料目前儲存在北美、西歐及亞太地區資料中心的 Azure 中。 如需有關資料儲存位置的詳細資訊，請參閱[我的資料在哪裡](http://o365datacentermap.azurewebsites.net/)？

## <a name="set-up-shifts"></a>設定倒班

### <a name="enable-or-disable-shifts-in-your-organization"></a>在組織中啟用或停用倒班

預設會針對貴組織中的所有團隊使用者啟用班次。 您可以在 Microsoft 團隊系統管理中心的 [[管理應用程式](../../manage-apps.md)] 頁面上關閉或開啟組織階層的 app。

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app** > **管理應用程式**]。
2. 在應用程式清單中，執行下列其中一項操作：

    - 若要關閉貴組織的倒班，請搜尋 [倒班] app，選取它，然後按一下 [**封鎖**]。
    - 若要為您的組織開啟倒班，請搜尋 [倒班] app，選取它，然後按一下 [**允許**]。

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>針對貴組織中的特定使用者啟用或停用班次

若要允許或封鎖貴組織中的特定使用者使用倒班，請確定您的組織已開啟 [[管理應用程式](../../manage-apps.md)] 頁面上的 [倒班]，然後建立自訂應用程式許可權原則，並將其指派給那些使用者。 若要深入瞭解，請參閱[在團隊中管理 app 許可權原則](../../teams-app-permission-policies.md)。

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>使用 FirstlineWorker 應用程式設定原則釘選到團隊

App 設定原則可讓您自訂小組，以醒目提示貴組織中的使用者最重要的 app。 原則中設定的應用程式會釘選到應用程式&mdash;行，以及小組行動客戶&mdash;端的右側列，使用者可以快速且輕鬆地存取。 
 
團隊包含內建的 FirstlineWorker 應用程式設定原則，您可以將它指派給貴組織中的第一線員工工作人員。 根據預設，原則包含活動、班次、聊天及呼叫 app。 

若要查看 FirstlineWorker 原則，請在 Microsoft 團隊系統管理中心的左導覽中，移至 [**小組 app** > **應用程式] 設定原則**。

![FirstlineWorker 應用程式設定原則的螢幕擷取畫面](../../media/firstline-worker-app-setup-policy.png "Microsoft 團隊系統管理中心的 FirstlineWorker 應用程式設定原則的螢幕擷取畫面")

#### <a name="assign-the-firstlineworker-policy-to-individual-users"></a>將 FirstlineWorker 原則指派給個別使用者

1. 在 Microsoft 團隊系統管理中心的左導覽中，前往 [**使用者**]，然後按一下使用者。
2. 在 [**指派的原則**] 旁，選擇 [**編輯**]。
3. 在 [**團隊 App 設定原則**] 底下，選取 [ **FirstlineWorker**]，然後選擇 [**儲存**]。

#### <a name="assign-the-firstlineworker-app-setup-policy-to-user-members-of-a-group"></a>將 FirstlineWorker 應用程式設定原則指派給群組的使用者成員

您可以將 FirstlineWorker 應用程式設定原則指派給群組的使用者成員（例如安全性群組），方法是連線到 Azure Active Directory PowerShell for Graph 模組及商務用 Skype PowerShell 模組。 如需有關使用 PowerShell 來管理團隊的詳細資訊，請參閱[團隊 PowerShell 概覽](../../teams-powershell-overview.md)。

在這個範例中，我們會將 FirstlineWorker 應用程式設定原則指派給 Contoso 第一線員工小組群組的所有使用者成員。

> [!NOTE]
> 請依照在[單一 Windows PowerShell 視窗中連線至 [所有 Office 365 服務]](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步驟，確認您首先連線至 [圖形模組] 和 [商務用 Skype] powershell 模組的 [Azure Active Directory PowerShell]。

取得特定群組的 GroupObjectId。
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
取得指定群組的成員。
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
將 FirstlineWorker 應用程式設定原則指派給群組的所有使用者成員。
```PowerShell
$members | ForEach-Object {Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
根據群組中的成員數目而定，此命令可能需要幾分鐘的時間執行。

## <a name="related-topics"></a>相關主題
- [倒班第一線員工工作者的協助](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
