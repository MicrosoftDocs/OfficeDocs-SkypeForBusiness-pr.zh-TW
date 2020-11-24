---
title: 針對 Google Workspace 設定 Microsoft 團隊會議附加元件
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: 瞭解如何設定 Google Workspace 的 Microsoft 團隊會議附加元件。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c86d707a4298d88d3ae0cff389bda73490390e4
ms.sourcegitcommit: 882ed439f8bba27b1cf0c14056c146267cacd359
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/24/2020
ms.locfileid: "49387286"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="e4efc-103">針對 Google Workspace 設定 Microsoft 團隊會議附加元件</span><span class="sxs-lookup"><span data-stu-id="e4efc-103">Set up Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="e4efc-104">使用 Microsoft 團隊會議附加元件可讓 Google 行事曆使用者從 Google Workspace 直接排程並加入 Microsoft 團隊會議。</span><span class="sxs-lookup"><span data-stu-id="e4efc-104">Using the Microsoft Teams meeting add-on lets Google calendar users schedule and join a Microsoft Teams meeting directly from Google Workspace.</span></span> <span data-ttu-id="e4efc-105">使用者將能夠存取團隊會議功能，包括影片和音訊會議、螢幕共用、會議聊天、數位白板等。</span><span class="sxs-lookup"><span data-stu-id="e4efc-105">Users will get access to Teams meetings features including video and audio conferencing, screen sharing, meeting chat, digital whiteboards, and more.</span></span> <span data-ttu-id="e4efc-106">保持連線與組織，以便在公司、學校和生活中共同完成工作。</span><span class="sxs-lookup"><span data-stu-id="e4efc-106">Stay connected and organized to get more done together across work, school, and life.</span></span>

<span data-ttu-id="e4efc-107">您必須先由小組管理員啟用 Google Workspace 的 Microsoft 團隊會議附加元件，才能讓租使用者存取 app。</span><span class="sxs-lookup"><span data-stu-id="e4efc-107">The Microsoft Teams meeting add-on for Google Workspace must be enabled by a Teams admin before tenant users can access the app.</span></span>

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a><span data-ttu-id="e4efc-108">在 Azure 入口網站中啟用或停用 Google Workspace 的 Microsoft 團隊會議附加元件</span><span class="sxs-lookup"><span data-stu-id="e4efc-108">Enable or disable Microsoft Teams meeting add-on for Google Workspace in the Azure portal</span></span>

<span data-ttu-id="e4efc-109">作為租使用者管理員，您可以使用 Azure 入口網站從貴組織的管理員帳戶啟用或停用 Google Workspace 的 Microsoft 團隊會議附加元件。</span><span class="sxs-lookup"><span data-stu-id="e4efc-109">As a tenant administrator, you can enable or disable a Microsoft Teams meeting add-on for Google Workspace from your organization's admin account using the Azure portal.</span></span>

<span data-ttu-id="e4efc-110">預設會啟用附加元件。</span><span class="sxs-lookup"><span data-stu-id="e4efc-110">The add-on is enabled by default.</span></span>

1. <span data-ttu-id="e4efc-111">登入 Azure 入口網站。</span><span class="sxs-lookup"><span data-stu-id="e4efc-111">Sign in to the Azure portal.</span></span>

2. <span data-ttu-id="e4efc-112">選取 [**企業應用程式**]  >  \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e4efc-112">Select **Enterprise applications** > **All applications**.</span></span>

3. <span data-ttu-id="e4efc-113">搜尋 **Google Workspace 的 Microsoft 團隊會議附加** 元件。</span><span class="sxs-lookup"><span data-stu-id="e4efc-113">Search for **Microsoft Teams meeting add-on for Google Workspace**.</span></span>

   ![顯示所有應用程式的 Azure 入口網站](media/aad-add-google-workspace.png)

4. <span data-ttu-id="e4efc-115">選取 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="e4efc-115">Select **Yes**.</span></span>

   ![顯示 google workspace 屬性的 Azure 入口網站](media/google-workspace-properties.png)

5. <span data-ttu-id="e4efc-117"> ([選用]) 停用附加元件，請在步驟4中選取 [ **否** ] 而不是 **[是]** 。</span><span class="sxs-lookup"><span data-stu-id="e4efc-117">(Optional) To disable the add-on, select **No** instead of **Yes** in Step 4.</span></span>

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a><span data-ttu-id="e4efc-118">使用 PowerShell 針對 Google Workspace 停用 Microsoft 團隊會議附加元件</span><span class="sxs-lookup"><span data-stu-id="e4efc-118">Disable Microsoft Teams meeting add-on for Google Workspace using PowerShell</span></span>

```powershell
Connect-AzureAD

$displayName = 'Microsoft Teams meeting add-on for Google Workspace'
$appId = '7969c887-ba98-48bb-8832-6c9239929d7c'

# Check if a service principal already exists for the app
$servicePrincipal = Get-AzureADServicePrincipal -Filter "appId eq '$appId'"
if ($servicePrincipal) {
    # Service principal exists already, disable it
    Set-AzureADServicePrincipal -ObjectId $servicePrincipal.ObjectId -AccountEnabled $false
    Write-Host "Disabled existing Service Principal \n"
} else {
    # Service principal does not yet exist, create it and disable it at the same time
    New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName
    $servicePrincipal = New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName -AccountEnabled $false
    Write-Host "Created and disabled the Service Principal \n"
}
```

<span data-ttu-id="e4efc-119">如需詳細資訊，請參閱 [使用 Azure PowerShell 建立 azure 服務主體](https://docs.microsoft.com/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0)。</span><span class="sxs-lookup"><span data-stu-id="e4efc-119">For more information, see [Create an Azure service principal with Azure PowerShell](https://docs.microsoft.com/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).</span></span>

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="e4efc-120">刪除 Google Workspace 的 Microsoft 團隊會議附加元件</span><span class="sxs-lookup"><span data-stu-id="e4efc-120">Delete the Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="e4efc-121">如需相關指示，請參閱 Google 檔 [刪除 Google Workspace Marketplace 應用程式](https://support.google.com/a/answer/6216211?hl=en) 。</span><span class="sxs-lookup"><span data-stu-id="e4efc-121">See the Google documentation [Delete a Google Workspace Marketplace app](https://support.google.com/a/answer/6216211?hl=en) for instructions.</span></span>
