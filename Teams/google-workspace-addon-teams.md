---
title: 設定 Google Workspace 的 Microsoft Teams 會議附加元件
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
description: 瞭解如何設定 Google Workspace 的 Microsoft Teams 會議附加元件。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e1b7024190ac51b89e09fafced86ffea13f5961
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120694"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="c70ed-103">設定 Google Workspace 的 Microsoft Teams 會議附加元件</span><span class="sxs-lookup"><span data-stu-id="c70ed-103">Set up Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="c70ed-104">使用 Microsoft Teams 會議附加元件可讓 Google 日曆使用者直接從 Google Workspace 排程並加入 Microsoft Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="c70ed-104">Using the Microsoft Teams meeting add-on lets Google calendar users schedule and join a Microsoft Teams meeting directly from Google Workspace.</span></span> <span data-ttu-id="c70ed-105">使用者可以存取 Teams 會議功能，包括視像和音訊會議、螢幕分享、會議聊天、數位白板等。</span><span class="sxs-lookup"><span data-stu-id="c70ed-105">Users will get access to Teams meetings features including video and audio conferencing, screen sharing, meeting chat, digital whiteboards, and more.</span></span> <span data-ttu-id="c70ed-106">保持聯繫並井井有條，以在公司、學校及生活中共同完成更多工作。</span><span class="sxs-lookup"><span data-stu-id="c70ed-106">Stay connected and organized to get more done together across work, school, and life.</span></span>

<span data-ttu-id="c70ed-107">在租使用者使用者存取應用程式之前，Google Workspace 的 Microsoft Teams 會議附加元件必須由 Teams 系統管理員啟用。</span><span class="sxs-lookup"><span data-stu-id="c70ed-107">The Microsoft Teams meeting add-on for Google Workspace must be enabled by a Teams admin before tenant users can access the app.</span></span>

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a><span data-ttu-id="c70ed-108">在 Azure 入口網站中啟用或停用 Google Workspace 的 Microsoft Teams 會議附加元件</span><span class="sxs-lookup"><span data-stu-id="c70ed-108">Enable or disable Microsoft Teams meeting add-on for Google Workspace in the Azure portal</span></span>

<span data-ttu-id="c70ed-109">做為租使用者系統管理員，您可以使用 Azure 入口網站，從組織的系統管理員帳戶啟用或停用 Microsoft Teams 會議附加元件。</span><span class="sxs-lookup"><span data-stu-id="c70ed-109">As a tenant administrator, you can enable or disable a Microsoft Teams meeting add-on for Google Workspace from your organization's admin account using the Azure portal.</span></span>

<span data-ttu-id="c70ed-110">附加元件預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="c70ed-110">The add-on is enabled by default.</span></span>

1. <span data-ttu-id="c70ed-111">請登錄 Azure 入口網站。</span><span class="sxs-lookup"><span data-stu-id="c70ed-111">Sign in to the Azure portal.</span></span>

2. <span data-ttu-id="c70ed-112">選取 **企業應用程式**  >  **所有應用程式**。</span><span class="sxs-lookup"><span data-stu-id="c70ed-112">Select **Enterprise applications** > **All applications**.</span></span>

3. <span data-ttu-id="c70ed-113">搜尋 Google Workspace 的 **Microsoft Teams 會議附加元件**。</span><span class="sxs-lookup"><span data-stu-id="c70ed-113">Search for **Microsoft Teams meeting add-on for Google Workspace**.</span></span>

   ![顯示所有應用程式的 Azure 入口網站](media/aad-add-google-workspace.png)

4. <span data-ttu-id="c70ed-115">選取 **是**。</span><span class="sxs-lookup"><span data-stu-id="c70ed-115">Select **Yes**.</span></span>

   ![顯示 Google 工作區屬性的 Azure 入口網站](media/google-workspace-properties.png)

5. <span data-ttu-id="c70ed-117"> (選擇性) 若要停用附加元件， **請選取步驟** 4 中的否，而不是 **是** 。</span><span class="sxs-lookup"><span data-stu-id="c70ed-117">(Optional) To disable the add-on, select **No** instead of **Yes** in Step 4.</span></span>

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a><span data-ttu-id="c70ed-118">使用 PowerShell 停用 Google 工作區的 Microsoft Teams 會議附加元件</span><span class="sxs-lookup"><span data-stu-id="c70ed-118">Disable Microsoft Teams meeting add-on for Google Workspace using PowerShell</span></span>

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

<span data-ttu-id="c70ed-119">詳細資訊，請參閱使用 [Azure PowerShell](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0)建立 Azure 服務主體 。</span><span class="sxs-lookup"><span data-stu-id="c70ed-119">For more information, see [Create an Azure service principal with Azure PowerShell](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).</span></span>

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="c70ed-120">刪除 Google Workspace 的 Microsoft Teams 會議附加元件</span><span class="sxs-lookup"><span data-stu-id="c70ed-120">Delete the Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="c70ed-121">請參閱 Google 檔 [刪除 Google Workspace Marketplace 應用程式](https://support.google.com/a/answer/6216211?hl=en) 以尋找相關指示。</span><span class="sxs-lookup"><span data-stu-id="c70ed-121">See the Google documentation [Delete a Google Workspace Marketplace app](https://support.google.com/a/answer/6216211?hl=en) for instructions.</span></span>