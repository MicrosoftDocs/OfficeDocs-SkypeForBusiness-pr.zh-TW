---
title: 為第一線員工大規模佈建 Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: keschm
description: 使用指令碼為第一線員工部署或佈建 Microsoft Teams 的指導方針。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: caecd0d97e760470604fa164e6356a59699e57ad
ms.sourcegitcommit: bc1d2e0478a429f981b53765e6194443b32ae35c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2020
ms.locfileid: "43122917"
---
# <a name="how-to-provision-teams-at-scale-for-firstline-workers"></a><span data-ttu-id="0270d-103">如何為第一線員工大規模佈建 Teams</span><span class="sxs-lookup"><span data-stu-id="0270d-103">How to provision Teams at scale for Firstline Workers</span></span>

<span data-ttu-id="0270d-104">您是否需要讓大量使用者快速加入 Microsoft Teams，並為他們設定簡化的使用體驗？</span><span class="sxs-lookup"><span data-stu-id="0270d-104">Do you need to rapidly onboard a large number of users to Microsoft Teams and configure a streamlined experience for them?</span></span> <span data-ttu-id="0270d-105">逐步完成下列指示，您就可以快速佈建身分識別、設定小組，並指派所有相關原則來控制使用者的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="0270d-105">You can quickly provision identities, provision teams, and assign all relevant policies to control the end user experience by walking through the following instructions.</span></span>

<span data-ttu-id="0270d-106">在本逐步解說中，您將了解如何：</span><span class="sxs-lookup"><span data-stu-id="0270d-106">In this walkthrough, you'll learn how to:</span></span>

- <span data-ttu-id="0270d-107">建立大量使用者。</span><span class="sxs-lookup"><span data-stu-id="0270d-107">Create a large number of users.</span></span>
- <span data-ttu-id="0270d-108">建立大量小組，並設定適當的頻道。</span><span class="sxs-lookup"><span data-stu-id="0270d-108">Create a large number of teams and set up the appropriate channels.</span></span>
- <span data-ttu-id="0270d-109">大規模指派授權。</span><span class="sxs-lookup"><span data-stu-id="0270d-109">Assign licensing at scale.</span></span>
- <span data-ttu-id="0270d-110">建立適當的小組訊息原則、應用程式設定原則和應用程式權限原則。</span><span class="sxs-lookup"><span data-stu-id="0270d-110">Create appropriate Teams Messaging Policies, App Setup Policies, and App Permission Policies.</span></span>
- <span data-ttu-id="0270d-111">對大量使用者套用這些原則。</span><span class="sxs-lookup"><span data-stu-id="0270d-111">Apply those policies to users at scale.</span></span>
- <span data-ttu-id="0270d-112">將大量使用者指派到指定的小組。</span><span class="sxs-lookup"><span data-stu-id="0270d-112">Assign a large number of users into a designated team.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0270d-113">必要條件</span><span class="sxs-lookup"><span data-stu-id="0270d-113">Prerequisites</span></span>

<span data-ttu-id="0270d-114">從[此位置](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/FLWTeamsScale.zip?raw=true)下載資產。</span><span class="sxs-lookup"><span data-stu-id="0270d-114">Download the assets from [this location](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/FLWTeamsScale.zip?raw=true).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0270d-115">上述連結中的指令碼是 Microsoft 所提供的原始指令碼，您必須根據個別需求加以修改。</span><span class="sxs-lookup"><span data-stu-id="0270d-115">The scripts in the link provided above are provided as-is by Microsoft, and must be modified for your individual needs.</span></span>

## <a name="technical-requirements"></a><span data-ttu-id="0270d-116">技術需求</span><span class="sxs-lookup"><span data-stu-id="0270d-116">Technical requirements</span></span>

- <span data-ttu-id="0270d-117">您的租用戶必須具備涵蓋 Microsoft Teams 的適當授權數量。</span><span class="sxs-lookup"><span data-stu-id="0270d-117">Your tenant must have the appropriate number of licenses available that include Microsoft Teams.</span></span> <span data-ttu-id="0270d-118">如果您還沒有這些授權，請依照此處的指示來啟動 [Office 365 E1 免費試用](e1-trial-license.md)。</span><span class="sxs-lookup"><span data-stu-id="0270d-118">If you do not already have these licenses, follow the instructions here to activate the [Office 365 E1 Free Trial](e1-trial-license.md).</span></span>
- <span data-ttu-id="0270d-119">使用者必須以 Azure AD 中的全域系統管理員或使用者系統管理員角色來採取這些步驟。</span><span class="sxs-lookup"><span data-stu-id="0270d-119">The user taking these steps must do so in the role of Global Admin or User Admin in Azure AD.</span></span>
- <span data-ttu-id="0270d-120">使用者必須有權在其本機電腦上安裝和設定軟體。</span><span class="sxs-lookup"><span data-stu-id="0270d-120">User must have the rights to install and configure software on their local machine.</span></span>

## <a name="step-by-step-process-overview"></a><span data-ttu-id="0270d-121">逐步程序概觀</span><span class="sxs-lookup"><span data-stu-id="0270d-121">Step-by-step process overview</span></span>

1. <span data-ttu-id="0270d-122">**設定您的環境**</span><span class="sxs-lookup"><span data-stu-id="0270d-122">**Setup Your Environment**</span></span>
    1. <span data-ttu-id="0270d-123">下載包含 PowerShell 指令碼範例和文件的 ZIP 檔案</span><span class="sxs-lookup"><span data-stu-id="0270d-123">Download the ZIP file containing the sample PowerShell scripts and documentation</span></span>
    1. <span data-ttu-id="0270d-124">設定認證</span><span class="sxs-lookup"><span data-stu-id="0270d-124">Setup credentials</span></span>
    1. <span data-ttu-id="0270d-125">設定本機環境</span><span class="sxs-lookup"><span data-stu-id="0270d-125">Configure local environment</span></span>
    1. <span data-ttu-id="0270d-126">設定 PowerShell 模組和環境變數</span><span class="sxs-lookup"><span data-stu-id="0270d-126">Configure PowerShell Modules and Environmental Variables</span></span>
    1. <span data-ttu-id="0270d-127">建立應用程式註冊</span><span class="sxs-lookup"><span data-stu-id="0270d-127">Create App Registration</span></span>
1. <span data-ttu-id="0270d-128">**建立及設定小組**</span><span class="sxs-lookup"><span data-stu-id="0270d-128">**Create and Setup Teams**</span></span>
    1. <span data-ttu-id="0270d-129">建立小組</span><span class="sxs-lookup"><span data-stu-id="0270d-129">Create Teams</span></span>
    1. <span data-ttu-id="0270d-130">為小組建立頻道</span><span class="sxs-lookup"><span data-stu-id="0270d-130">Create Channels for Teams</span></span>
1. <span data-ttu-id="0270d-131">**建立小組原則**</span><span class="sxs-lookup"><span data-stu-id="0270d-131">**Create Teams Policies**</span></span>
    1. <span data-ttu-id="0270d-132">建立小組訊息原則</span><span class="sxs-lookup"><span data-stu-id="0270d-132">Create Teams Messaging Policies</span></span>
    1. <span data-ttu-id="0270d-133">建立小組應用程式設定原則</span><span class="sxs-lookup"><span data-stu-id="0270d-133">Create Teams App Setup Policies</span></span>
    1. <span data-ttu-id="0270d-134">建立小組應用程式權限原則</span><span class="sxs-lookup"><span data-stu-id="0270d-134">Create Teams App Permission Policies</span></span>
1. <span data-ttu-id="0270d-135">**建立及設定使用者**</span><span class="sxs-lookup"><span data-stu-id="0270d-135">**Create and Setup Users**</span></span>
    1. <span data-ttu-id="0270d-136">建立使用者和安全性群組</span><span class="sxs-lookup"><span data-stu-id="0270d-136">Create users and security groups</span></span>
    1. <span data-ttu-id="0270d-137">透過群組型授權將授權指派給使用者</span><span class="sxs-lookup"><span data-stu-id="0270d-137">Assign licensing to users via group-based licensing</span></span>
1. <span data-ttu-id="0270d-138">**指派使用者和原則**</span><span class="sxs-lookup"><span data-stu-id="0270d-138">**Assign Users and Policies**</span></span>
    1. <span data-ttu-id="0270d-139">將使用者指派給小組</span><span class="sxs-lookup"><span data-stu-id="0270d-139">Assign users to Teams</span></span>
    1. <span data-ttu-id="0270d-140">將原則指派給使用者和群組</span><span class="sxs-lookup"><span data-stu-id="0270d-140">Assign policies to User and Groups</span></span>
1. <span data-ttu-id="0270d-141">**測試與驗證**</span><span class="sxs-lookup"><span data-stu-id="0270d-141">**Test and Validate**</span></span>
    1. <span data-ttu-id="0270d-142">檢查錯誤</span><span class="sxs-lookup"><span data-stu-id="0270d-142">Check for errors</span></span>
    1. <span data-ttu-id="0270d-143">以測試使用者的身分登入 Teams</span><span class="sxs-lookup"><span data-stu-id="0270d-143">Login to Teams with a test user</span></span>

## <a name="set-up-your-environment"></a><span data-ttu-id="0270d-144">設定您的環境</span><span class="sxs-lookup"><span data-stu-id="0270d-144">Set up your environment</span></span>

<span data-ttu-id="0270d-145">下列步驟可讓您設定您的環境：</span><span class="sxs-lookup"><span data-stu-id="0270d-145">The following steps will allow you to set up your environment:</span></span>

### <a name="download-zip-file-containing-sample-powershell-scripts"></a><span data-ttu-id="0270d-146">下載包含 PowerShell 指令碼範例的 .zip 檔案</span><span class="sxs-lookup"><span data-stu-id="0270d-146">Download .zip file containing sample PowerShell scripts</span></span>

<span data-ttu-id="0270d-147">在您繼續進行之前，您必須先在[此位置](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/FLWTeamsScale.zip?raw=true)下載指令碼。</span><span class="sxs-lookup"><span data-stu-id="0270d-147">Before you can proceed, you'll need to download the scripts at [this location](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/FLWTeamsScale.zip?raw=true).</span></span>

### <a name="setup-credentials"></a><span data-ttu-id="0270d-148">設定認證</span><span class="sxs-lookup"><span data-stu-id="0270d-148">Setup Credentials</span></span>

<span data-ttu-id="0270d-149">為了方便起見，我們已在本文件和指令碼範例中，選擇建立包含您認證的參考檔案。</span><span class="sxs-lookup"><span data-stu-id="0270d-149">In this document and the sample scripts we've chosen to create a reference file that contains your credentials in order to make things easier.</span></span> <span data-ttu-id="0270d-150">此方式可讓您在本機存放區中維護認證，而不必再對所有服務端點進行驗證。</span><span class="sxs-lookup"><span data-stu-id="0270d-150">This technique removes the need for you to authenticate to all the various service endpoints while maintaining the credentials in a local store.</span></span> <span data-ttu-id="0270d-151">若要執行後續的指令碼，您將必須使用您和您環境獨有的認證來更新該參考檔案。</span><span class="sxs-lookup"><span data-stu-id="0270d-151">In order to run the subsequent scripts, you'll need to update that reference file with the credentials that are unique to you and your environment.</span></span> <span data-ttu-id="0270d-152">在後續的每個指令碼中，系統會使用稱為 **GetCreds** 的 helper 函式來讀取適當認證，而這些認證會用來與各種服務連線。</span><span class="sxs-lookup"><span data-stu-id="0270d-152">From within each subsequent script, the appropriate credentials are read with the helper function  we've called **GetCreds**, and those credentials are used to connect to the various services.</span></span>

<span data-ttu-id="0270d-153">不同服務需要不同認證的情形並不常見。</span><span class="sxs-lookup"><span data-stu-id="0270d-153">It's not uncommon for different services to require different credentials.</span></span> <span data-ttu-id="0270d-154">例如，您可能會有用於 MicrosoftTeams、AzureAD 和 MSonline 的不同認證，在這種情況下，您可以執行 SetCred 將每個憑證檔儲存為對本身有意義的名稱。</span><span class="sxs-lookup"><span data-stu-id="0270d-154">For example you might have different credentials for MicrosoftTeams, AzureAD, and MSonline, in which case you can run SetCred saving each credential file with its own meaningful name.</span></span>

<span data-ttu-id="0270d-155">例如：SetCreds msol-cred.xml、SetCreds azuread-cred.xml、SetCreds teams-cred.xml</span><span class="sxs-lookup"><span data-stu-id="0270d-155">Examples: SetCreds msol-cred.xml SetCreds azuread-cred.xml SetCreds teams-cred.xml</span></span>

> [!NOTE]
> <span data-ttu-id="0270d-156">用於認證的帳戶不可要求 MFA。</span><span class="sxs-lookup"><span data-stu-id="0270d-156">The account used for the credentials cannot require MFA.</span></span>

<span data-ttu-id="0270d-157">下列範例說明各種指令碼如何使用已儲存的認證來進行驗證：</span><span class="sxs-lookup"><span data-stu-id="0270d-157">Here is an example of how the various scripts then use the saved credentials to authenticate:</span></span>

```azurepowershell
# Connect to MicrosoftTeams
$teams_cred = GetCreds teams-cred.xml
Connect-MicrosoftTeams -Credential $teams_cred
```

<span data-ttu-id="0270d-158">若要設定認證，請完成下列動作：</span><span class="sxs-lookup"><span data-stu-id="0270d-158">In order to set your credentials, complete the following:</span></span>

1. <span data-ttu-id="0270d-159">在 .zip 檔案資產中尋找 **SetCreds.ps1**。</span><span class="sxs-lookup"><span data-stu-id="0270d-159">Find the **SetCreds.ps1** in the .zip file assets.</span></span>
1. <span data-ttu-id="0270d-160">從 PowerShell 執行 **SetCreds.ps1** 指令碼來儲存認證。</span><span class="sxs-lookup"><span data-stu-id="0270d-160">From PowerShell run the **SetCreds.ps1** script to save your credentials.</span></span>
    1. <span data-ttu-id="0270d-161">系統會提示您「執行 "Export-Clixml" 作業...」，然後您必須輸入 'Y' 來核准。</span><span class="sxs-lookup"><span data-stu-id="0270d-161">You'll be prompted with "Performing the operation "Export-Clixml"..." and you'll need to enter 'Y' to approve.</span></span>

### <a name="configure-the-local-environment"></a><span data-ttu-id="0270d-162">設定本機環境</span><span class="sxs-lookup"><span data-stu-id="0270d-162">Configure the local environment</span></span>

1. <span data-ttu-id="0270d-163">在 .zip 檔案資產中尋找 **SetConfig.ps1**。</span><span class="sxs-lookup"><span data-stu-id="0270d-163">Find the **SetConfig.ps1** in the .zip file assets.</span></span>
1. <span data-ttu-id="0270d-164">從 PowerShell 執行下列命令，並以您的特定資訊取代括弧中的項目。</span><span class="sxs-lookup"><span data-stu-id="0270d-164">From PowerShell run the following command, replacing the bracketed entries with your specific information.</span></span>
    1. <span data-ttu-id="0270d-165">**SetConfig.ps1** -tenantName [您的租用戶名稱] -rootPath "[Git 存放庫根目錄的完整路徑]"</span><span class="sxs-lookup"><span data-stu-id="0270d-165">**SetConfig.ps1** -tenantName [your tenant name] -rootPath "[full path to the root of the git repo]"</span></span>

<span data-ttu-id="0270d-166">例如：`.\SetConfig.ps1 -tenantName contoso.onmicrosoft.com -rootPath "C:\data\source\FLWTeamsScale"`</span><span class="sxs-lookup"><span data-stu-id="0270d-166">For example: `.\SetConfig.ps1 -tenantName contoso.onmicrosoft.com -rootPath "C:\data\source\FLWTeamsScale"`</span></span>

### <a name="configure-powershell-modules-and-environmental-variables"></a><span data-ttu-id="0270d-167">設定 PowerShell 模組和環境變數</span><span class="sxs-lookup"><span data-stu-id="0270d-167">Configure PowerShell modules and environmental variables</span></span>

<span data-ttu-id="0270d-168">在您進行下一步之前，您必須安裝並連線到數個 PowerShell 模組，包括 Azure AD、MSAL、MSCloudUtils 和 MicrosoftTeams。</span><span class="sxs-lookup"><span data-stu-id="0270d-168">Before you go further, you'll need to install and connect to several PowerShell modules, including Azure AD, MSAL, MSCloudUtils, and MicrosoftTeams.</span></span>

1. <span data-ttu-id="0270d-169">在 .zip 檔案資產中尋找 **ConfigurePowerShellModules.ps1**。</span><span class="sxs-lookup"><span data-stu-id="0270d-169">Find the **ConfigurePowerShellModules.ps1** in the .zip file assets.</span></span>
1. <span data-ttu-id="0270d-170">使用您的變數來編輯及取代下列環境變數：</span><span class="sxs-lookup"><span data-stu-id="0270d-170">Edit and replace the following environmental variables with your variables:</span></span>
1. <span data-ttu-id="0270d-171">從 PowerShell 中執行 **ConfigurePowerShellModules.ps1** 指令碼。</span><span class="sxs-lookup"><span data-stu-id="0270d-171">From PowerShell, run the **ConfigurePowerShellModules.ps1** script.</span></span>

## <a name="create-and-set-up-teams"></a><span data-ttu-id="0270d-172">建立及設定小組</span><span class="sxs-lookup"><span data-stu-id="0270d-172">Create and set up Teams</span></span>

<span data-ttu-id="0270d-173">為了與您的第一線員工交流並進行共同作業，您必須先建立一系列的小組，並為這些小組新增標準頻道，我們將在下一節中說明。</span><span class="sxs-lookup"><span data-stu-id="0270d-173">In order to communicate and collaborate with your Firstline Workers, you will first need to establish a series of Teams and add standard Channels to those teams, which we'll walk through next.</span></span>

### <a name="create-teams"></a><span data-ttu-id="0270d-174">建立小組</span><span class="sxs-lookup"><span data-stu-id="0270d-174">Create teams</span></span>

<span data-ttu-id="0270d-175">小組是組織內人員、內容和工具的集合。</span><span class="sxs-lookup"><span data-stu-id="0270d-175">Teams are a collection of people, content, and tools within your organization.</span></span> <span data-ttu-id="0270d-176">對於大部分以第一線員工為中心的組織而言，最佳做法是以實體位置為中心來定位小組。</span><span class="sxs-lookup"><span data-stu-id="0270d-176">For most Firstline Worker-centric organizations, it is best practice to anchor a Team around a physical location.</span></span> <span data-ttu-id="0270d-177">例如，為下列每一項建立小組：</span><span class="sxs-lookup"><span data-stu-id="0270d-177">For example, a Team for each of the following:</span></span>

- <span data-ttu-id="0270d-178">商店</span><span class="sxs-lookup"><span data-stu-id="0270d-178">Store</span></span>
- <span data-ttu-id="0270d-179">配送中心</span><span class="sxs-lookup"><span data-stu-id="0270d-179">Distribution Center</span></span>
- <span data-ttu-id="0270d-180">製造廠</span><span class="sxs-lookup"><span data-stu-id="0270d-180">Manufacturing Plant</span></span>
- <span data-ttu-id="0270d-181">醫院</span><span class="sxs-lookup"><span data-stu-id="0270d-181">Hospital</span></span>
- <span data-ttu-id="0270d-182">雜貨店</span><span class="sxs-lookup"><span data-stu-id="0270d-182">Grocery Store</span></span>

<span data-ttu-id="0270d-183">*最佳做法討論*：設計小組時，務必注意[小組限制和規格](limits-specifications-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="0270d-183">*Best Practice Discussion*: When designing your teams, it's important to keep in mind [Teams limits and specifications](limits-specifications-teams.md).</span></span> <span data-ttu-id="0270d-184">對於較小的組織，可使用整個組織作為小組來簡化溝通工作，並讓實體位置結構變得更完整。</span><span class="sxs-lookup"><span data-stu-id="0270d-184">For smaller organizations, an org-wide team can be used to streamline communication and complement a physical location structure.</span></span> <span data-ttu-id="0270d-185">對其他組織來說，結構良好的實體位置小組命名慣例，有助於公司透過交叉發佈輕鬆地同時與多個小組通訊。</span><span class="sxs-lookup"><span data-stu-id="0270d-185">For others, a structured physical location Team naming convention helps assist Corporate Communications with Cross Posting to multiple teams simultaneously with ease.</span></span> <span data-ttu-id="0270d-186">例如，若要以所有「美國」地區的小組為目標，您可以搜尋名稱中有「美國」的所有小組，並對其進行交叉發佈。</span><span class="sxs-lookup"><span data-stu-id="0270d-186">For example, you can search and cross-post to all Teams with US in the name to target all US locations.</span></span> <span data-ttu-id="0270d-187">您可以在[這裡](https://support.office.com/article/cross-post-a-channel-conversation-in-teams-9c1252a3-67ef-498e-a7c1-dd7147b3d295)找到有關交叉發佈的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="0270d-187">More information on cross-posting can be found [here](https://support.office.com/article/cross-post-a-channel-conversation-in-teams-9c1252a3-67ef-498e-a7c1-dd7147b3d295).</span></span>

#### <a name="steps-to-create-teams"></a><span data-ttu-id="0270d-188">建立小組的步驟</span><span class="sxs-lookup"><span data-stu-id="0270d-188">Steps to create teams</span></span>

1. <span data-ttu-id="0270d-189">在資產中尋找 **Teams Information.csv** 檔案。</span><span class="sxs-lookup"><span data-stu-id="0270d-189">Find the **Teams Information.csv** file in the assets.</span></span>
1. <span data-ttu-id="0270d-190">使用您組織的特定資訊來更新 **Teams Information.csv** 檔案中的資訊。</span><span class="sxs-lookup"><span data-stu-id="0270d-190">Update the information in the **Teams Information.csv** file with your organization's specific information.</span></span> <span data-ttu-id="0270d-191">請記住上述的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="0270d-191">Keep in mind our best practices above.</span></span>
1. <span data-ttu-id="0270d-192">尋找 **CreateTeams.ps1** 指令碼。</span><span class="sxs-lookup"><span data-stu-id="0270d-192">Find the **CreateTeams.ps1** script.</span></span>
1. <span data-ttu-id="0270d-193">從 PowerShell 中執行 **CreateTeams.ps1** 指令碼。</span><span class="sxs-lookup"><span data-stu-id="0270d-193">From PowerShell, run the **CreateTeams.ps1** script.</span></span>

### <a name="create-channels-for-teams"></a><span data-ttu-id="0270d-194">為小組建立頻道</span><span class="sxs-lookup"><span data-stu-id="0270d-194">Create channels for teams</span></span>

<span data-ttu-id="0270d-195">頻道是小組內的專用區段，可保存依特定主題、專案、分項等等而統整的交談。</span><span class="sxs-lookup"><span data-stu-id="0270d-195">Channels are dedicated sections within a team to keep conversations organized by specific topic, project, discipline, and more.</span></span> <span data-ttu-id="0270d-196">每個小組都會自動取得「一般」頻道，但是您可以根據企業需求在此處自訂您的結構。</span><span class="sxs-lookup"><span data-stu-id="0270d-196">Every Team automatically gets a General channel, but from there you can customize your structure according to the needs of your business.</span></span> <span data-ttu-id="0270d-197">例如，您的額外頻道結構可能包括：</span><span class="sxs-lookup"><span data-stu-id="0270d-197">For example, your additional channel structure could include:</span></span>

- <span data-ttu-id="0270d-198">**製造** - 安全、產線 1、產線 2、公司通訊、訓練</span><span class="sxs-lookup"><span data-stu-id="0270d-198">**Manufacturing** - Safety, Line 1, Line 2, Corporate Communications, Training</span></span>
- <span data-ttu-id="0270d-199">**雜貨** - 麵包、農產品、肉類、公司通訊、訓練</span><span class="sxs-lookup"><span data-stu-id="0270d-199">**Grocery** - Bakery, Produce, Meat, Corporate Communications, Training</span></span>
- <span data-ttu-id="0270d-200">**醫療保健** - 護士、醫生、加護病房 1、加護病房 2</span><span class="sxs-lookup"><span data-stu-id="0270d-200">**Healthcare** - Nurses, Doctors, Critical Care Unit 1, Critical Care Unit 2</span></span>
- <span data-ttu-id="0270d-201">**飯店觀光** - 櫃台、維護、房務、停車和行李服務、公司通訊、訓練</span><span class="sxs-lookup"><span data-stu-id="0270d-201">**Hospitality** - Front Desk, Maintenance, Housekeeping, Valet and Baggage, Corporate Communications, Training</span></span>
- <span data-ttu-id="0270d-202">**零售** - 商店前方、商店後方、公司通訊、訓練</span><span class="sxs-lookup"><span data-stu-id="0270d-202">**Retail** - Front of Store, Back of Store, Corporate Communications, Training</span></span>

> [!NOTE]
> <span data-ttu-id="0270d-203">頻道不應視為安全性界限。</span><span class="sxs-lookup"><span data-stu-id="0270d-203">Channels should not be thought of as a security boundary.</span></span> <span data-ttu-id="0270d-204">這是您組織工人以進行共同作業的方式。</span><span class="sxs-lookup"><span data-stu-id="0270d-204">They are a means of organizing your workers for the purposes of collaboration.</span></span>

<span data-ttu-id="0270d-205">*最佳做法討論*：設計頻道結構時，務必要讓一切簡單，特別是當您想要讓許多使用者上手時。</span><span class="sxs-lookup"><span data-stu-id="0270d-205">*Best Practice Discussion*: When designing your channel structure, it's important to keep things simple, especially when you're looking to onboard a lot of users.</span></span> <span data-ttu-id="0270d-206">避免針對每個狀況、角色或主題建立頻道，以將訓練的需求降至最低。</span><span class="sxs-lookup"><span data-stu-id="0270d-206">Resist the urge to create channels for every situation, role, or topic in order to minimize the need for training.</span></span> <span data-ttu-id="0270d-207">一開始最多挑選 3-5 個頻道。</span><span class="sxs-lookup"><span data-stu-id="0270d-207">Pick 3-5 channels at most to get started.</span></span> <span data-ttu-id="0270d-208">您可以在需求增加時輕鬆地建立其他頻道。</span><span class="sxs-lookup"><span data-stu-id="0270d-208">Additional channels can easily be created as the need arises.</span></span> <span data-ttu-id="0270d-209">事實上，您現在就可以獨自使用一般通道了！</span><span class="sxs-lookup"><span data-stu-id="0270d-209">In fact, it's okay to just use the General channel alone for now!</span></span>

#### <a name="steps-to-create-channels-for-teams"></a><span data-ttu-id="0270d-210">建立小組頻道的步驟</span><span class="sxs-lookup"><span data-stu-id="0270d-210">Steps to Create Channels for Teams</span></span>

1. <span data-ttu-id="0270d-211">在 .zip 檔案資產中尋找 **TeamsChannels.csv** 檔案。</span><span class="sxs-lookup"><span data-stu-id="0270d-211">Find the **TeamsChannels.csv** file in the .zip file assets.</span></span>
1. <span data-ttu-id="0270d-212">使用您組織的特定資訊來更新 **TeamsChannels.csv** 檔案。</span><span class="sxs-lookup"><span data-stu-id="0270d-212">Update the **TeamsChannels.csv** file with your organization's specific information.</span></span> <span data-ttu-id="0270d-213">請記住上述的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="0270d-213">Keep in mind our best practices above.</span></span>
1. <span data-ttu-id="0270d-214">在 .zip 檔案資產中尋找 **CreateTeamsChannels.ps1**指令碼。</span><span class="sxs-lookup"><span data-stu-id="0270d-214">Find the **CreateTeamsChannels.ps1** script in the .zip file assets.</span></span>
1. <span data-ttu-id="0270d-215">從 PowerShell 中執行 **TeamsChannels.ps1** 指令碼。</span><span class="sxs-lookup"><span data-stu-id="0270d-215">From PowerShell, run the **TeamsChannels.ps1** script.</span></span>

## <a name="create-teams-policies"></a><span data-ttu-id="0270d-216">建立小組原則</span><span class="sxs-lookup"><span data-stu-id="0270d-216">Create Teams policies</span></span>

<span data-ttu-id="0270d-217">如果您是系統管理員，您可以使用 Microsoft Teams 中的小組原則來控制您組織中使用者可看見和可執行的項目。</span><span class="sxs-lookup"><span data-stu-id="0270d-217">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization see and can.</span></span> <span data-ttu-id="0270d-218">例如，您可以控制要將哪些應用程式釘選到桌面或網頁瀏覽器的左側滑軌，或行動裝置的底部工具列，以簡化加入大量使用者的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="0270d-218">For example, you can control which applications are pinned to the left rail on your Desktop or Web browser, or the bottom bar on mobile devices, in order to simplify the end user experience when onboarding a large amount of users.</span></span> <span data-ttu-id="0270d-219">其中有些原則可使用 PowerShell 建立，但其他原則必須在 Teams 系統管理員主控台上手動建立。</span><span class="sxs-lookup"><span data-stu-id="0270d-219">Some of these policies can be created with PowerShell, and others have to be manually created in the Teams Admin Console.</span></span>

<span data-ttu-id="0270d-220">*最佳做法討論*：針對下列每個原則，我們將選擇實際建立兩個原則：一個用於第一線員工，一個用於第一線管理者。</span><span class="sxs-lookup"><span data-stu-id="0270d-220">*Best Practice Discussion*: For each of the following policies, we're choosing to actually create two policies: one for Firstline Workers and one for Firstline Managers.</span></span> <span data-ttu-id="0270d-221">您可以根據自己的喜好，選擇建立任意數量的原則。</span><span class="sxs-lookup"><span data-stu-id="0270d-221">You can choose to create as many or as few as you like.</span></span> <span data-ttu-id="0270d-222">對大部分客戶而言，兩個是較佳的起點 (即使您一開始對每個群組都進行相同的設定)。</span><span class="sxs-lookup"><span data-stu-id="0270d-222">For most customers, two is a good place to start, even if you give the same settings to each group initially.</span></span> <span data-ttu-id="0270d-223">隨著您對 Teams 愈來愈熟悉，您可以選擇進一步區別他們的經驗，若已建立此兩個原則，則可讓此動作變得更簡單。</span><span class="sxs-lookup"><span data-stu-id="0270d-223">As your experience with Teams grows, you may choose to differentiate their experience further and having the two separate policies already created can make that simpler.</span></span>

### <a name="create-teams-message-policies"></a><span data-ttu-id="0270d-224">建立小組訊息原則</span><span class="sxs-lookup"><span data-stu-id="0270d-224">Create Teams message policies</span></span>

<span data-ttu-id="0270d-225">管理原則是用來控制 Microsoft Teams. 中使用者可使用的聊天及頻道訊息功能。</span><span class="sxs-lookup"><span data-stu-id="0270d-225">Messaging policies are used to control which chat and channel messaging features are available to users in Microsoft Teams.</span></span>

<span data-ttu-id="0270d-226">*最佳做法討論*：雖然您可以使用自動建立的預設全域原則，但我們選擇使用下列步驟建立自訂原則，以便為第一線管理者和第一線員工提供更隱密、簡單且與眾不同的使用體驗。</span><span class="sxs-lookup"><span data-stu-id="0270d-226">*Best Practice Discussion*: While you can use the default Global policy that is created automatically, we have opted to create a custom policy using the steps below to provide a more locked down, simple, and differentiated experience for Firstline Managers and Firstline Workers.</span></span>

#### <a name="steps-to-create-teams-message-policies"></a><span data-ttu-id="0270d-227">建立小組訊息原則的步驟</span><span class="sxs-lookup"><span data-stu-id="0270d-227">Steps to Create Teams Message Policies</span></span>

1. <span data-ttu-id="0270d-228">在 .zip 檔案資產中尋找 **TeamsMessagingPolicies.csv** 檔案。</span><span class="sxs-lookup"><span data-stu-id="0270d-228">Find the **TeamsMessagingPolicies.csv** file in the .zip file assets.</span></span>
1. <span data-ttu-id="0270d-229">使用您組織的特定資訊更新 **TeamsMessagingPolicies.csv** 檔案。</span><span class="sxs-lookup"><span data-stu-id="0270d-229">Update the **TeamsMessagingPolicies.csv** file with your organization's specific information.</span></span> <span data-ttu-id="0270d-230">您可以在[這裡](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams#messaging-policy-settings)找到一些不同選項的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="0270d-230">Additional information on some of the various options can be found [here](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams#messaging-policy-settings).</span></span>
1. <span data-ttu-id="0270d-231">在資產中尋找 **CreateTeamsMessagePolicies.ps1**指令碼。</span><span class="sxs-lookup"><span data-stu-id="0270d-231">Find the **CreateTeamsMessagePolicies.ps1** script in the assets.</span></span>
1. <span data-ttu-id="0270d-232">從 PowerShell 中執行 **TeamsMessagePolicies.ps1** 指令碼。</span><span class="sxs-lookup"><span data-stu-id="0270d-232">From PowerShell, run the **TeamsMessagePolicies.ps1** script.</span></span>

### <a name="create-teams-app-setup-policies"></a><span data-ttu-id="0270d-233">建立 Teams 應用程式設定原則</span><span class="sxs-lookup"><span data-stu-id="0270d-233">Create Teams app setup policies</span></span>

<span data-ttu-id="0270d-234">如果您是系統管理員，您可以使用應用程式設定原則來執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="0270d-234">As an admin, you can use app setup policies to do the following:</span></span>

- <span data-ttu-id="0270d-235">自訂 Teams 以強調對使用者而言最重要的應用程式。</span><span class="sxs-lookup"><span data-stu-id="0270d-235">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="0270d-236">您可以選擇要釘選的應用程式，並設定其顯示順序。</span><span class="sxs-lookup"><span data-stu-id="0270d-236">You choose the apps to pin and set the order in which they appear.</span></span> <span data-ttu-id="0270d-237">釘選應用程式可讓您展示組織中使用者所需的應用程式，包括由第三方或您組織開發人員所建立的應用程式。</span><span class="sxs-lookup"><span data-stu-id="0270d-237">Pinning apps lets you showcase apps that users in your organization need, including those built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="0270d-238">控制使用者是否可以將應用程式釘選到 Teams。</span><span class="sxs-lookup"><span data-stu-id="0270d-238">Control whether users can pin apps to Teams.</span></span>

<span data-ttu-id="0270d-239">應用程式會釘選到應用程式列。</span><span class="sxs-lookup"><span data-stu-id="0270d-239">Apps are pinned to the app bar.</span></span> <span data-ttu-id="0270d-240">這是位於 Teams 桌面用戶端側邊和 Teams 行動用戶端 (iOS 和 Android) 底部的應用程式列。</span><span class="sxs-lookup"><span data-stu-id="0270d-240">This is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="0270d-241">Teams 桌面用戶端</span><span class="sxs-lookup"><span data-stu-id="0270d-241">Teams Desktop Client</span></span>  |         |<span data-ttu-id="0270d-242">Teams 行動用戶端</span><span class="sxs-lookup"><span data-stu-id="0270d-242">Teams Mobile Client</span></span>  |
|---------|---------|---------|
|![將應用程式釘選到 *應用程式* 列的 Teams 桌面用戶端螢幕擷取畫面。](media/FLW-Teams-Desktop-Client.png)         |         |![將應用程式釘選到 *底部* 工具列的 Teams 桌面用戶端螢幕擷取畫面。](media/FLW-Teams-Mobile-Client.png) |

<span data-ttu-id="0270d-245">*最佳做法討論*：您可以在 Microsoft Teams 系統管理中心管理應用程式設定原則。</span><span class="sxs-lookup"><span data-stu-id="0270d-245">*Best Practice Discussion*: You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="0270d-246">這些原則無法使用 PowerShell 建立。</span><span class="sxs-lookup"><span data-stu-id="0270d-246">They aren't able to be created with PowerShell.</span></span> <span data-ttu-id="0270d-247">您可以使用全域 (預設為全組織) 原則或建立自訂原則，並指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="0270d-247">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="0270d-248">除非您建立並指派自訂原則，否則您組織中的使用者將會自動獲派全域原則。</span><span class="sxs-lookup"><span data-stu-id="0270d-248">Users in your organization will automatically be assigned to the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="0270d-249">根據我們的目的，我們要為第一線員工和第一線管理者建立兩個新的原則，為他們提供更簡單且更精簡的體驗，以便輕鬆地同時加入大量使用者。</span><span class="sxs-lookup"><span data-stu-id="0270d-249">For our purposes, we are creating two new policies for Firstline Workers and Firstline Managers, in order to provide them a simpler and more streamlined experience to ease onboarding a large number of users simultaneously.</span></span> <span data-ttu-id="0270d-250">您可以選擇根據業務需求來自訂體驗。</span><span class="sxs-lookup"><span data-stu-id="0270d-250">You can choose to customize the experience as your business needs.</span></span>

#### <a name="create-the-firstline-manager-app-setup-policy"></a><span data-ttu-id="0270d-251">建立第一線管理員的應用程式設定原則</span><span class="sxs-lookup"><span data-stu-id="0270d-251">Create the Firstline Manager app setup policy</span></span>

<span data-ttu-id="0270d-252">您可以根據業務需求來自訂下列設定。</span><span class="sxs-lookup"><span data-stu-id="0270d-252">The following settings can be customized to meet your business needs.</span></span> <span data-ttu-id="0270d-253">我們已根據最佳做法選擇了一些建議選項，讓您可更輕鬆地加入大量新使用者。</span><span class="sxs-lookup"><span data-stu-id="0270d-253">We have chosen some recommended options based on best practices and to improve the ease of onboarding new users at scale.</span></span> <span data-ttu-id="0270d-254">如需詳細資訊，請按一下[這裡](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy)。</span><span class="sxs-lookup"><span data-stu-id="0270d-254">For more information, click [here](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy).</span></span>

1. <span data-ttu-id="0270d-255">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至  **[Teams 應用程式]** > **[設定原則]**。</span><span class="sxs-lookup"><span data-stu-id="0270d-255">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="0270d-256">按一下  **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="0270d-256">Click **Add**.</span></span>  
3. <span data-ttu-id="0270d-257">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="0270d-257">Enter a name and description for the policy.</span></span> <span data-ttu-id="0270d-258">範例：**第一線管理者的應用程式設定原則**。</span><span class="sxs-lookup"><span data-stu-id="0270d-258">As an example: **Firstline Manager App Setup Policy**.</span></span>
<span data-ttu-id="0270d-259">![第一線管理者的應用程式設定原則影像。](media/FLW-FLM-App-Setup-Policy.png)</span><span class="sxs-lookup"><span data-stu-id="0270d-259">![Firstline manager app setup policy image.](media/FLW-FLM-App-Setup-Policy.png)</span></span>

4. <span data-ttu-id="0270d-260">關閉 **[上傳自訂應用程式]**。</span><span class="sxs-lookup"><span data-stu-id="0270d-260">Turn off **Upload custom apps**.</span></span>
5. <span data-ttu-id="0270d-261">關閉 **[允許使用者釘選]**。</span><span class="sxs-lookup"><span data-stu-id="0270d-261">Turn off **Allow user pinning**.</span></span>
<span data-ttu-id="0270d-262">![允許使用者釘選的切換影像。](media/FLW-Allow-User-Pinning.png)</span><span class="sxs-lookup"><span data-stu-id="0270d-262">![Allow user pinning switch image.](media/FLW-Allow-User-Pinning.png)</span></span>

6. <span data-ttu-id="0270d-263">新增 **Shifts**應用程式 (如果尚未列出的話)。</span><span class="sxs-lookup"><span data-stu-id="0270d-263">If it's not already listed, add the **Shifts** app.</span></span> <span data-ttu-id="0270d-264">如需有關 **Shifts** 的詳細資訊，請按一下[這裡](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="0270d-264">For more information about **Shifts**, click [here](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md).</span></span>
<span data-ttu-id="0270d-265">![新增釘選應用程式的畫面，並顯示 [新增] 按鈕旁邊已列出 Shifts 應用程式。](media/FLW-Add-Pinned-Apps.png)</span><span class="sxs-lookup"><span data-stu-id="0270d-265">![Add pinned apps screen, showing the Shifts app listed next to an Add button.](media/FLW-Add-Pinned-Apps.png)</span></span>

7. <span data-ttu-id="0270d-266">移除 [通話] 功能 (如果有的話)。</span><span class="sxs-lookup"><span data-stu-id="0270d-266">Remove Calling, if it appears.</span></span> <span data-ttu-id="0270d-267">注意：移除此功能不會為使用者停用此功能，但會防止其顯示在應用程式列上，藉此簡化使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="0270d-267">Note: removing this feature will not disable it for the user, but will prevent it from appearing on the app bar to simplify the end user experience.</span></span>
8. <span data-ttu-id="0270d-268">按照下列順序排列應用程式，以指定應用程式在 Teams 應用程式列中的順序，然後按一下  **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="0270d-268">Arrange the apps in the following order to dictate their order in the Teams App Bar, and then click **Save**.</span></span>
    1. <span data-ttu-id="0270d-269">活動</span><span class="sxs-lookup"><span data-stu-id="0270d-269">Activity</span></span>
    1. <span data-ttu-id="0270d-270">聊天</span><span class="sxs-lookup"><span data-stu-id="0270d-270">Chat</span></span>
    1. <span data-ttu-id="0270d-271">Teams</span><span class="sxs-lookup"><span data-stu-id="0270d-271">Teams</span></span>
    1. <span data-ttu-id="0270d-272">行事曆</span><span class="sxs-lookup"><span data-stu-id="0270d-272">Calendar</span></span>
    1. <span data-ttu-id="0270d-273">Shifts ![依序列出管理者應用程式的螢幕擷取畫面](media/FLW-Manager-Pinned-Apps.png)</span><span class="sxs-lookup"><span data-stu-id="0270d-273">Shifts ![Screenshot of the manager apps list in order.](media/FLW-Manager-Pinned-Apps.png)</span></span>

#### <a name="create-the-firstline-worker-app-setup-policy"></a><span data-ttu-id="0270d-274">建立第一線員工的應用程式設定原則</span><span class="sxs-lookup"><span data-stu-id="0270d-274">Create the Firstline Worker app setup policy</span></span>

<span data-ttu-id="0270d-275">您可以根據業務需求來自訂下列設定。</span><span class="sxs-lookup"><span data-stu-id="0270d-275">The following settings can be customized to meet your business needs.</span></span> <span data-ttu-id="0270d-276">我們已根據最佳做法選擇了一些建議選項，讓您可更輕鬆地加入大量新使用者。</span><span class="sxs-lookup"><span data-stu-id="0270d-276">We have chosen some recommended options based on best practices and to improve the ease of onboarding new users at scale.</span></span> <span data-ttu-id="0270d-277">如需詳細資訊，請按一下[這裡](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy)。</span><span class="sxs-lookup"><span data-stu-id="0270d-277">For more information, click [here](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy).</span></span>

1. <span data-ttu-id="0270d-278">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至  **[Teams 應用程式]** > **[設定原則]**。</span><span class="sxs-lookup"><span data-stu-id="0270d-278">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="0270d-279">按一下  **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="0270d-279">Click **Add**.</span></span>
3. <span data-ttu-id="0270d-280">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="0270d-280">Enter a name and description for the policy.</span></span> <span data-ttu-id="0270d-281">範例：**第一線員工的應用程式設定原則**。</span><span class="sxs-lookup"><span data-stu-id="0270d-281">As an example: **Firstline Worker App Setup Policy**.</span></span>
<span data-ttu-id="0270d-282">![第一線員工的應用程式設定原則影像。](media/FLW-FLW-App-Setup-Policy.png)</span><span class="sxs-lookup"><span data-stu-id="0270d-282">![Firstline worker app setup policy image.](media/FLW-FLW-App-Setup-Policy.png)</span></span>

4. <span data-ttu-id="0270d-283">關閉 **[上傳自訂應用程式]**。</span><span class="sxs-lookup"><span data-stu-id="0270d-283">Turn off **Upload custom apps**.</span></span>
5. <span data-ttu-id="0270d-284">關閉 **[允許使用者釘選]**。</span><span class="sxs-lookup"><span data-stu-id="0270d-284">Turn off **Allow user pinning**.</span></span>
<span data-ttu-id="0270d-285">![允許使用者釘選的切換影像。](media/FLW-Allow-User-Pinning.png)</span><span class="sxs-lookup"><span data-stu-id="0270d-285">![Allow user pinning switch image.](media/FLW-Allow-User-Pinning.png)</span></span>

6. <span data-ttu-id="0270d-286">新增 **Shifts**應用程式 (如果尚未列出的話)。</span><span class="sxs-lookup"><span data-stu-id="0270d-286">If it's not already listed, add the **Shifts** app.</span></span> <span data-ttu-id="0270d-287">如需有關 **Shifts** 的詳細資訊，請按一下這裡。</span><span class="sxs-lookup"><span data-stu-id="0270d-287">For more information about **Shifts**, click here.</span></span>
<span data-ttu-id="0270d-288">![新增釘選應用程式的畫面，並顯示 [新增] 按鈕旁邊已列出 Shifts 應用程式。](media/FLW-Add-Pinned-Apps.png)</span><span class="sxs-lookup"><span data-stu-id="0270d-288">![Add pinned apps screen, showing the Shifts app listed next to an Add button.](media/FLW-Add-Pinned-Apps.png)</span></span>

7. <span data-ttu-id="0270d-289">移除 [會議] 和 [通話] \(如果有的話)。</span><span class="sxs-lookup"><span data-stu-id="0270d-289">Remove Meetings and Calling, if they appear.</span></span> <span data-ttu-id="0270d-290">注意：移除這些功能不會為使用者停用這些功能，但會防止其顯示在應用程式列上，藉此簡化使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="0270d-290">Note: removing these features will not disable them for the user, but will prevent them from appearing on the app bar to simplify the end user experience.</span></span>
8. <span data-ttu-id="0270d-291">按照下列順序排列應用程式，以指定應用程式在 Teams 應用程式列中的順序，然後按一下  **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="0270d-291">Arrange the apps in the following order to dictate their order in the Teams App Bar, and then click **Save**.</span></span>
    1. <span data-ttu-id="0270d-292">活動</span><span class="sxs-lookup"><span data-stu-id="0270d-292">Activity</span></span>
    1. <span data-ttu-id="0270d-293">聊天</span><span class="sxs-lookup"><span data-stu-id="0270d-293">Chat</span></span>
    1. <span data-ttu-id="0270d-294">Teams</span><span class="sxs-lookup"><span data-stu-id="0270d-294">Teams</span></span>
    1. <span data-ttu-id="0270d-295">Shifts ![依序列出員工應用程式的螢幕擷取畫面。](media/FLW-Worker-Pinned-Apps.png)</span><span class="sxs-lookup"><span data-stu-id="0270d-295">Shifts ![Screenshot of the worker apps list in order.](media/FLW-Worker-Pinned-Apps.png)</span></span>

### <a name="create-app-permission-policies"></a><span data-ttu-id="0270d-296">建立應用程式權限原則</span><span class="sxs-lookup"><span data-stu-id="0270d-296">Create app permission policies</span></span>

<span data-ttu-id="0270d-297">身為系統管理員，您可以使用應用程式權限原則來控制組織中 Microsoft Teams 使用者可使用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="0270d-297">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="0270d-298">您可以允許或封鎖所有應用程式，或是由 Microsoft、第三方和您組織發行的特定應用程式。</span><span class="sxs-lookup"><span data-stu-id="0270d-298">You can allow or block all apps, or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="0270d-299">當您封鎖應用程式時，擁有原則的使用者將無法從 Teams 應用程式商店安裝該應用程式。</span><span class="sxs-lookup"><span data-stu-id="0270d-299">When you block an app, users who have the policy are unable to install it from the Teams app store.</span></span> <span data-ttu-id="0270d-300">您必須是全域系統管理員或 Teams 服務系統管理員，才能管理這些原則。</span><span class="sxs-lookup"><span data-stu-id="0270d-300">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="0270d-301">*最佳做法討論*：您可以在 Microsoft Teams 系統管理中心管理應用程式設定原則。</span><span class="sxs-lookup"><span data-stu-id="0270d-301">*Best Practice Discussion*: You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="0270d-302">這些原則無法使用 PowerShell 建立。</span><span class="sxs-lookup"><span data-stu-id="0270d-302">They aren't able to be created with PowerShell.</span></span> <span data-ttu-id="0270d-303">您可以使用全域 (預設為全組織) 原則或建立自訂原則，並指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="0270d-303">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="0270d-304">除非您建立並指派自訂原則，否則貴組織中的使用者將會自動取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="0270d-304">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="0270d-305">根據我們的目的，我們要為第一線員工和第一線管理者建立兩個新的原則，為他們提供安全且更精簡的體驗，以便輕鬆地同時加入大量使用者。</span><span class="sxs-lookup"><span data-stu-id="0270d-305">For our purposes, we are creating two new policies for Firstline Workers and Firstline Managers in order to provide a secure and more streamlined experience to ease onboarding a large number of users simultaneously.</span></span> <span data-ttu-id="0270d-306">當然，您可以選擇根據您的業務需求來自訂體驗。</span><span class="sxs-lookup"><span data-stu-id="0270d-306">You can of course choose to customize the experience as your business needs.</span></span>

#### <a name="create-the-firstline-manager-app-permission-policy"></a><span data-ttu-id="0270d-307">建立第一線管理者的應用程式權限原則</span><span class="sxs-lookup"><span data-stu-id="0270d-307">Create the Firstline Manager app permission policy</span></span>

<span data-ttu-id="0270d-308">您可以根據業務需求來自訂下列設定。</span><span class="sxs-lookup"><span data-stu-id="0270d-308">The following settings can be customized to meet your business needs.</span></span> <span data-ttu-id="0270d-309">以下是根據最佳做法提供的建議選項，可讓您更輕鬆地加入大量新使用者。</span><span class="sxs-lookup"><span data-stu-id="0270d-309">These are some recommended options based on best practices that can improve the ease of onboarding new users at scale.</span></span> <span data-ttu-id="0270d-310">如需詳細資訊，請按一下[這裡](teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0270d-310">For more information, click [here](teams-app-permission-policies.md).</span></span>

1. <span data-ttu-id="0270d-311">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至  **[Teams 應用程式]** > **[權限原則]**。</span><span class="sxs-lookup"><span data-stu-id="0270d-311">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="0270d-312">按一下  **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="0270d-312">Click **Add**.</span></span>
<span data-ttu-id="0270d-313">![顯示新增應用程式權限原則頁面，其中包含 Microsoft、第三方和租用戶應用程式的區段。](media/FLW-add-app-permission-policy.png)</span><span class="sxs-lookup"><span data-stu-id="0270d-313">![Shows the add app permission policy page, with sections for Microsoft, third-party, and tenant apps.](media/FLW-add-app-permission-policy.png)</span></span>

3. <span data-ttu-id="0270d-314">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="0270d-314">Enter a name and description for the policy.</span></span> <span data-ttu-id="0270d-315">範例：第一線管理者的應用程式權限原則。</span><span class="sxs-lookup"><span data-stu-id="0270d-315">As an example: Firstline Manager App Permission Policy.</span></span>
4. <span data-ttu-id="0270d-316">在 [Microsoft 應用程式] 底下，選取 **[允許所有應用程式]**。</span><span class="sxs-lookup"><span data-stu-id="0270d-316">Under Microsoft apps, select **Allow all apps**.</span></span>
5. <span data-ttu-id="0270d-317">在 [第三方應用程式] 底下，選取 **[允許所有應用程式]**。</span><span class="sxs-lookup"><span data-stu-id="0270d-317">Under Third-party apps, select **Allow all apps**.</span></span>
6. <span data-ttu-id="0270d-318">在 [租用戶應用程式] 底下，選取 **[允許所有應用程式]**。</span><span class="sxs-lookup"><span data-stu-id="0270d-318">Under Tenant apps, select **Allow all apps**.</span></span>
7. <span data-ttu-id="0270d-319">按一下  **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="0270d-319">Click **Save**.</span></span>

#### <a name="create-the-firstline-worker-app-permission-policy"></a><span data-ttu-id="0270d-320">建立第一線員工的應用程式權限原則</span><span class="sxs-lookup"><span data-stu-id="0270d-320">Create the Firstline Worker App Permission Policy</span></span>

<span data-ttu-id="0270d-321">您可以根據業務需求來自訂下列設定。</span><span class="sxs-lookup"><span data-stu-id="0270d-321">The following settings can be customized to meet your business needs.</span></span> <span data-ttu-id="0270d-322">以下是根據最佳做法提供的建議選項，可讓您更輕鬆地加入大量新使用者。</span><span class="sxs-lookup"><span data-stu-id="0270d-322">These are some recommended options based on best practices that can improve the ease of onboarding new users at scale.</span></span> <span data-ttu-id="0270d-323">如需詳細資訊，請按一下[這裡](teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0270d-323">For more information, click [here](teams-app-permission-policies.md).</span></span>

1. <span data-ttu-id="0270d-324">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至  **[Teams 應用程式]** > **[權限原則]**。</span><span class="sxs-lookup"><span data-stu-id="0270d-324">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="0270d-325">按一下  **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="0270d-325">Click **Add**.</span></span>
<span data-ttu-id="0270d-326">![顯示新增應用程式權限原則頁面，其中包含 Microsoft、第三方和租用戶應用程式的區段。](media/FLW-add-app-permission-policy.png)</span><span class="sxs-lookup"><span data-stu-id="0270d-326">![Shows the add app permission policy page, with sections for Microsoft, third-party, and tenant apps.](media/FLW-add-app-permission-policy.png)</span></span>

3. <span data-ttu-id="0270d-327">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="0270d-327">Enter a name and description for the policy.</span></span> <span data-ttu-id="0270d-328">範例：第一線員工的應用程式權限原則。</span><span class="sxs-lookup"><span data-stu-id="0270d-328">As an example: Firstline Worker App Permission Policy.</span></span>
4. <span data-ttu-id="0270d-329">在 [Microsoft 應用程式] 底下，選取 **[允許所有應用程式]**。</span><span class="sxs-lookup"><span data-stu-id="0270d-329">Under Microsoft apps, select **Allow all apps**.</span></span>
5. <span data-ttu-id="0270d-330">在 [第三方應用程式] 底下，選取 **[封鎖所有應用程式]**。</span><span class="sxs-lookup"><span data-stu-id="0270d-330">Under Third-party apps, select **Block all apps**.</span></span>
6. <span data-ttu-id="0270d-331">在 [租用戶應用程式] 底下，選取 **[允許所有應用程式]**。</span><span class="sxs-lookup"><span data-stu-id="0270d-331">Under Tenant apps, select **Allow all apps**.</span></span>
7. <span data-ttu-id="0270d-332">按一下  **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="0270d-332">Click **Save**.</span></span>

## <a name="create-and-set-up-users"></a><span data-ttu-id="0270d-333">建立及設定使用者</span><span class="sxs-lookup"><span data-stu-id="0270d-333">Create and set up users</span></span>

### <a name="create-user-and-security-groups"></a><span data-ttu-id="0270d-334">建立使用者和安全性群組</span><span class="sxs-lookup"><span data-stu-id="0270d-334">Create user and security groups</span></span>

<span data-ttu-id="0270d-335">若要在 Teams 中與大量使用者合作，您必須先在 Azure AD 中建立使用者。</span><span class="sxs-lookup"><span data-stu-id="0270d-335">To work with a large amount of users in Teams you first need to have the users created in Azure AD.</span></span> <span data-ttu-id="0270d-336">佈建大量使用者的方法有很多種，但我們會著重說明以下內容：</span><span class="sxs-lookup"><span data-stu-id="0270d-336">There are many ways to provision a large number of users, but we're going to highlight the following:</span></span>

- <span data-ttu-id="0270d-337">如果這些使用者已存在於下列其中一個 HR 系統中，請使用下列連結來設定使用者佈建：</span><span class="sxs-lookup"><span data-stu-id="0270d-337">If these users already exist in one of the following HR systems, use the following links to set up user provisioning:</span></span>
  - <span data-ttu-id="0270d-338">SAP 成功因素 - [教學課程：將 SAP SuccessFactors 設定為 Active Directory 使用者佈建](https://docs.microsoft.com/azure/active-directory/saas-apps/sap-successfactors-inbound-provisioning-tutorial)。</span><span class="sxs-lookup"><span data-stu-id="0270d-338">SAP Success Factors - [Tutorial: Configure SAP SuccessFactors to Active Directory user provisioning](https://docs.microsoft.com/azure/active-directory/saas-apps/sap-successfactors-inbound-provisioning-tutorial).</span></span>
  - <span data-ttu-id="0270d-339">Workday - [教學課程：設定 Workday 以自動佈建使用者](https://docs.microsoft.com/azure/active-directory/saas-apps/workday-inbound-tutorial)。</span><span class="sxs-lookup"><span data-stu-id="0270d-339">Workday - [Tutorial: Configure Workday for automatic user provisioning](https://docs.microsoft.com/azure/active-directory/saas-apps/workday-inbound-tutorial).</span></span>
- <span data-ttu-id="0270d-340">如果其他系統中有您的使用者資訊，請繼續執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="0270d-340">If you have your user information in other systems, proceed with the following steps.</span></span>

<span data-ttu-id="0270d-341">若要以更有效率的方式管理大量使用者，您必須為第一線員工和第一線管理者建立兩個安全性群組，並按照下列步驟將這些使用者直接佈建到安全性群組：</span><span class="sxs-lookup"><span data-stu-id="0270d-341">In order to manage these users at scale more effectively, you need to create two security groups for Firstline Workers and Firstline Managers, and provision those users into the security groups directly, following these steps:</span></span>

1. <span data-ttu-id="0270d-342">在 .zip 檔案資產中尋找 **SecurityGroups.csv** 檔案。</span><span class="sxs-lookup"><span data-stu-id="0270d-342">Find the **SecurityGroups.csv** file in the .zip file assets.</span></span>
1. <span data-ttu-id="0270d-343">使用您組織的特定資訊更新 **SecurityGroups.csv** 檔案。</span><span class="sxs-lookup"><span data-stu-id="0270d-343">Update the **SecurityGroups.csv** file with your organization's specific information.</span></span>
    1. <span data-ttu-id="0270d-344">請務必更新 **[MessagePolicy]**、**[AppPermissionPolicy]** 和 **[AppSetupPolicy]** 欄位，以對應您之前建立的適當原則。</span><span class="sxs-lookup"><span data-stu-id="0270d-344">Make sure to update the **MessagePolicy**, **AppPermissionPolicy**, and **AppSetupPolicy** fields to map to the appropriate policies you created earlier.</span></span>
    1. <span data-ttu-id="0270d-345">請務必更新 **[LicensePlan]** 欄位，以反映您要如何將授權提供給每位使用者。</span><span class="sxs-lookup"><span data-stu-id="0270d-345">Make sure to update the **LicensePlan** field to reflect the licensing that you intend to give each of these users.</span></span> <span data-ttu-id="0270d-346">如需產品名稱與服務方案識別碼的詳細資訊，請參閱[此處](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)的文件。</span><span class="sxs-lookup"><span data-stu-id="0270d-346">For more information on product names and service plan identifiers, review the documentation [here](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>
1. <span data-ttu-id="0270d-347">在 .zip 檔案資產中尋找 **Users.csv** 檔案。</span><span class="sxs-lookup"><span data-stu-id="0270d-347">Find the **Users.csv** file in the .zip file assets.</span></span>
1. <span data-ttu-id="0270d-348">使用您組織的特定資訊來更新 **Users.csv** 檔案。</span><span class="sxs-lookup"><span data-stu-id="0270d-348">Update the **Users.csv** file with your organization's specific information.</span></span>
    1. <span data-ttu-id="0270d-349">根據預設，我們提供的指令碼會建立一個使用者和暫時性密碼，第一次登入時必須變更此密碼。</span><span class="sxs-lookup"><span data-stu-id="0270d-349">By default, the script we've provided will create a user with a temporary password that must be changed on first login.</span></span> <span data-ttu-id="0270d-350">如果您不想要使用預設密碼，請編輯 **CreateUsers.ps1** 指令碼，以符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="0270d-350">If you don't want to use the default password, edit the **CreateUsers.ps1** script to meet your requirements.</span></span>
    1. <span data-ttu-id="0270d-351">請務必更新 SecurityGroup 欄位，以反映先前建立的適當名稱。</span><span class="sxs-lookup"><span data-stu-id="0270d-351">Make sure to update the SecurityGroup field to reflect the appropriate name created earlier.</span></span>
1. <span data-ttu-id="0270d-352">透過 PowerShell 執行資產中的 **CreateUsers.ps1** 指令碼。</span><span class="sxs-lookup"><span data-stu-id="0270d-352">From PowerShell, run the script **CreateUsers.ps1** from assets.</span></span>

### <a name="assign-licensing-to-users-by-group-based-licensing"></a><span data-ttu-id="0270d-353">透過群組型授權將授權指派給使用者</span><span class="sxs-lookup"><span data-stu-id="0270d-353">Assign licensing to users by Group-Based licensing</span></span>

<span data-ttu-id="0270d-354">Microsoft 付費雲端服務 (例如 Office 365、企業版行動力 + 安全性、Dynamics 365 及其他類似產品) 都需要授權。</span><span class="sxs-lookup"><span data-stu-id="0270d-354">Microsoft paid cloud services, such as Office 365, Enterprise Mobility + Security, Dynamics 365, and other similar products, require licenses.</span></span> <span data-ttu-id="0270d-355">這些授權會指派給需要存取這些服務的每位使用者。</span><span class="sxs-lookup"><span data-stu-id="0270d-355">These licenses are assigned to each user who needs access to these services.</span></span> <span data-ttu-id="0270d-356">若要管理授權，系統管理員可使用其中一個管理入口網站 (Office 或 Azure) 和 PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0270d-356">To manage licenses, administrators use one of the management portals (Office or Azure) and PowerShell cmdlets.</span></span> <span data-ttu-id="0270d-357">Azure Active Directory (Azure AD) 是支援所有 Microsoft 雲端服務身分識別管理的基礎結構。</span><span class="sxs-lookup"><span data-stu-id="0270d-357">Azure Active Directory (Azure AD) is the underlying infrastructure that supports identity management for all Microsoft cloud services.</span></span> <span data-ttu-id="0270d-358">Azure AD 會儲存使用者授權指派狀態的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0270d-358">Azure AD stores information about license assignment states for users.</span></span>

<span data-ttu-id="0270d-359">為了大規模啟用授權，Azure AD 目前已包含群組型授權，而且基於這個原因，我們已在本文前面建立了安全性群組。</span><span class="sxs-lookup"><span data-stu-id="0270d-359">In order to enable licensing at scale, Azure AD now includes group-based licensing, and for this reason we created the security groups earlier in this article.</span></span> <span data-ttu-id="0270d-360">您可以將一個或多個產品授權指派給群組。</span><span class="sxs-lookup"><span data-stu-id="0270d-360">You can assign one or more product licenses to a group.</span></span> <span data-ttu-id="0270d-361">Azure AD 可確保授權會指派給群組的所有成員。</span><span class="sxs-lookup"><span data-stu-id="0270d-361">Azure AD ensures that the licenses are assigned to all members of the group.</span></span> <span data-ttu-id="0270d-362">任何加入群組的新成員都會獲派適當的授權。</span><span class="sxs-lookup"><span data-stu-id="0270d-362">Any new members who join the group are assigned the appropriate licenses.</span></span> <span data-ttu-id="0270d-363">如果成員離開該群組，授權也會移除。</span><span class="sxs-lookup"><span data-stu-id="0270d-363">Licenses are removed from members who leave the group.</span></span> <span data-ttu-id="0270d-364">此授權管理免除透過 PowerShell 自動化授權管理的必要，並根據每個使用者來反映組織和部門結構中的變更。</span><span class="sxs-lookup"><span data-stu-id="0270d-364">This licensing management eliminates the need for automating license management via PowerShell to reflect changes in the organization and departmental structure on a per-user basis.</span></span>

## <a name="assign-users-and-policies"></a><span data-ttu-id="0270d-365">指派使用者和原則</span><span class="sxs-lookup"><span data-stu-id="0270d-365">Assign Users and Policies</span></span>

### <a name="assigning-users-to-teams"></a><span data-ttu-id="0270d-366">將使用者指派給小組</span><span class="sxs-lookup"><span data-stu-id="0270d-366">Assigning users to teams</span></span>

<span data-ttu-id="0270d-367">現在您已建立使用者並建立了小組，您可以將所有使用者放在適當的小組中。</span><span class="sxs-lookup"><span data-stu-id="0270d-367">Now that you've created the users and created the Teams, it's time to put all the users in the appropriate Teams.</span></span>

1. <span data-ttu-id="0270d-368">在 .zip 檔案資產中尋找 **Users.csv** 檔案，並確認與該檔案中的小組有正確的對應。</span><span class="sxs-lookup"><span data-stu-id="0270d-368">Find the **Users.csv** file in the .zip file assets and make sure you have accurate mapping to Teams in this file.</span></span>
1. <span data-ttu-id="0270d-369">透過 PowerShell 執行 .zip 檔案資產中的 **AssignUserstoTeams.ps1** 指令碼。</span><span class="sxs-lookup"><span data-stu-id="0270d-369">From PowerShell, run the script **AssignUserstoTeams.ps1** from the .zip file assets.</span></span>

### <a name="assign-teams-policies-to-users"></a><span data-ttu-id="0270d-370">指派小組原則給使用者</span><span class="sxs-lookup"><span data-stu-id="0270d-370">Assign Teams policies to users</span></span>

<span data-ttu-id="0270d-371">現在您已建立使用者和用來修改小組體驗的原則，接著您可以將這些原則指派給正確的使用者。</span><span class="sxs-lookup"><span data-stu-id="0270d-371">Now that you've created the users and the policies to modify their experience in Teams, it's time to assign those policies to the correct users.</span></span>

1. <span data-ttu-id="0270d-372">在 .zip 檔案資產中尋找 **SecurityGroups.csv** 檔案，並確認您的原則正確地對應至群組。</span><span class="sxs-lookup"><span data-stu-id="0270d-372">Find the **SecurityGroups.csv** file in the .zip file assets and make sure you have accurate mapping of the policies to the groups.</span></span>
1. <span data-ttu-id="0270d-373">透過 PowerShell 執行 .zip 檔案資產中的 **AssignPoliciestoUsers.ps1**。</span><span class="sxs-lookup"><span data-stu-id="0270d-373">From PowerShell, run the script **AssignPoliciestoUsers.ps1** from the .zip file assets.</span></span>

## <a name="test-and-validate"></a><span data-ttu-id="0270d-374">測試與驗證</span><span class="sxs-lookup"><span data-stu-id="0270d-374">Test and validate</span></span>

### <a name="check-for-errors"></a><span data-ttu-id="0270d-375">檢查錯誤</span><span class="sxs-lookup"><span data-stu-id="0270d-375">Check for errors</span></span>

<span data-ttu-id="0270d-376">當您執行較舊的指令碼時，系統會將錯誤或例外狀況寫入到 .csv 檔案，並置於 .zip 檔案資產的 [記錄] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="0270d-376">As you ran the earlier scripts, errors or exceptions were written to a .csv file located in the logs folder of the .zip file assets.</span></span> <span data-ttu-id="0270d-377">您可以使用此檔案來調查可能發生的任何問題。</span><span class="sxs-lookup"><span data-stu-id="0270d-377">This file can be used to investigate any issues that may have occurred.</span></span>

<span data-ttu-id="0270d-378">例如，如果您嘗試建立已存在於租用戶的小組，就可能會發生例外狀況。</span><span class="sxs-lookup"><span data-stu-id="0270d-378">An example of an exception could be if you tried to create a team that already existed in your tenant.</span></span>

1. <span data-ttu-id="0270d-379">尋找 **[記錄]** 資料夾，然後檢視其中包含的任何 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="0270d-379">Find the **Logs** folder and review any .csv file it may contain.</span></span> <span data-ttu-id="0270d-380">如果沒有例外狀況，表示您可能無法在此找到例外狀況檔案。</span><span class="sxs-lookup"><span data-stu-id="0270d-380">If there are no exceptions, you may not find an exception file here.</span></span>

### <a name="login-to-teams-with-a-test-user"></a><span data-ttu-id="0270d-381">以測試使用者的身分登入 Teams</span><span class="sxs-lookup"><span data-stu-id="0270d-381">Login to Teams with a test user</span></span>

<span data-ttu-id="0270d-382">完成所有步驟之後，您就可以驗證您所完成的工作了。</span><span class="sxs-lookup"><span data-stu-id="0270d-382">Now that you've completed all the steps, it's time to verify the work you've completed.</span></span>

1. <span data-ttu-id="0270d-383">選取先前清單中的使用者，然後以該使用者的認證登入 Teams。</span><span class="sxs-lookup"><span data-stu-id="0270d-383">Select a user from your earlier list and log into Teams with that user's credentials.</span></span>
1. <span data-ttu-id="0270d-384">確認 Teams 的外觀與風格是否與您所預期的相同。</span><span class="sxs-lookup"><span data-stu-id="0270d-384">Verify the look and feel of Teams is what you expected.</span></span> <span data-ttu-id="0270d-385">如果不是，請檢閱**建立小組原則**和**指派小組原則給使用者**區段。</span><span class="sxs-lookup"><span data-stu-id="0270d-385">If not, review the **Create Teams Policies** and the **Assign Teams Policies to Users** sections.</span></span>
1. <span data-ttu-id="0270d-386">驗證使用者是否屬於正確的小組。</span><span class="sxs-lookup"><span data-stu-id="0270d-386">Verify the user is in the correct team.</span></span> <span data-ttu-id="0270d-387">如果不是，請檢閱**建立及設定使用者**和**將使用者指派給小組**區段。</span><span class="sxs-lookup"><span data-stu-id="0270d-387">If not, review the **Create and Setup Users** and **Assign Users to Teams** sections.</span></span>
