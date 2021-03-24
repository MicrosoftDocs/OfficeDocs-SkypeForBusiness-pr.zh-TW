---
title: 在 Microsoft 365 或 Office 365 部署商務用 Skype 用戶端
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: '瞭解如何在小型、中型和大型組織中規劃及部署商務用 Skype，以及讓使用者使用 Skype。 '
ms.openlocfilehash: 7a2ba51a315b77c501735be863f342c1bdb1548f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097289"
---
# <a name="deploy-the-skype-for-business-client-in-microsoft-365-or-office-365"></a><span data-ttu-id="d5d73-103">在 Microsoft 365 或 Office 365 中部署商務用 Skype 用戶端</span><span class="sxs-lookup"><span data-stu-id="d5d73-103">Deploy the Skype for Business client in Microsoft 365 or Office 365</span></span>

<span data-ttu-id="d5d73-104">本文說明系統管理員如何將商務用 Skype **[](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** 應用程式部署給貴組織的人員的選項。</span><span class="sxs-lookup"><span data-stu-id="d5d73-104">This article explains options for how you, the **[admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)**, can deploy the Skype for Business app to the people in your organization.</span></span>
  
<span data-ttu-id="d5d73-105">在將商務用 Skype 部署給使用者之前，請確定您已完成設定商務用 [Skype Online](set-up-skype-for-business-online.md)一文的步驟 1-3。</span><span class="sxs-lookup"><span data-stu-id="d5d73-105">Before you deploy Skype for Business to your users, make sure you've done steps 1-3 in the article [Set up Skype for Business Online](set-up-skype-for-business-online.md).</span></span> <span data-ttu-id="d5d73-106">如此一來，商務用 Skype 就會與網域一起設定，每個人都會擁有他們的授權，而您將為貴組織的 [商務](configure-presence-in-skype-for-business-online.md) 用 Skype Online 設定 IM 和設定目前狀態。</span><span class="sxs-lookup"><span data-stu-id="d5d73-106">This way, Skype for Business will be set up with your domain, everyone will have their licenses, and you will have configured IM and [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md) for your organization.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d5d73-107">使用者若要安裝商務用 Skype 應用程式，他們必須是電腦或裝置上的當地系統管理員。</span><span class="sxs-lookup"><span data-stu-id="d5d73-107">For users to install the Skype for Business app, they need to be local admins on their PC or device.</span></span> <span data-ttu-id="d5d73-108">或者，他們必須是可以在電腦或裝置上安裝 App 的當地群組的一部分。</span><span class="sxs-lookup"><span data-stu-id="d5d73-108">Or they will need to be part of a local group that can install apps on their PC or devices.</span></span> <span data-ttu-id="d5d73-109">如果您的使用者不允許在裝置上安裝軟體，您必須為使用者安裝商務用 Skype 應用程式。</span><span class="sxs-lookup"><span data-stu-id="d5d73-109">If your users aren't allowed to install software on their devices, you'll need to install the Skype for Business app for them.</span></span> 
  
## <a name="for-most-small-and-medium-sized-businesses"></a><span data-ttu-id="d5d73-110">適用于大多數中小型企業</span><span class="sxs-lookup"><span data-stu-id="d5d73-110">For most small and medium-sized businesses</span></span>

 <span data-ttu-id="d5d73-111">**逐步安裝指示：** 如果您有中小型企業，建議您直接要求使用者在您的電腦上安裝商務用 Skype 應用程式。</span><span class="sxs-lookup"><span data-stu-id="d5d73-111">**Step-by-step installation instructions:** If you have a small or medium-sized business, we recommend that you simply ask your users to install the Skype for Business app on their PC.</span></span> <span data-ttu-id="d5d73-112">指向這些指示：[安裝商務用 Skype。](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)</span><span class="sxs-lookup"><span data-stu-id="d5d73-112">Point them to these instructions: [Install Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb).</span></span> <span data-ttu-id="d5d73-113">如果他們使用的是 Mac，請指向設定 [Lync for Mac 2011 for Office 365](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88)。</span><span class="sxs-lookup"><span data-stu-id="d5d73-113">If they are using Macs, point them to [Set up Lync for Mac 2011 for Office 365](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88).</span></span> <span data-ttu-id="d5d73-114">商務用 Skype 應用程式會與 Office App 的其餘部分分開安裝。</span><span class="sxs-lookup"><span data-stu-id="d5d73-114">The Skype for Business app is installed separately from the rest of the Office apps.</span></span>
  
 <span data-ttu-id="d5d73-115">**適用于企業客戶的 Microsoft 365 應用程式：** 如果您的公司使用的是包含 Microsoft 365 企業版 App 的 Office 365 方案 ，例如 E3 方案，則使用者下載並安裝 Word、Excel、PowerPoint 等商務用 Skype App 時，即會同時安裝。這也表示他們無法卸載商務用 Skype，除非他們卸載所有 Office。</span><span class="sxs-lookup"><span data-stu-id="d5d73-115">**Microsoft 365 Apps for enterprise customers:** If your business is using an Office 365 plan that includes Microsoft 365 Apps for enterprise, such as the E3 plan, the Skype for Business app is installed at the same time your users download and install Word, Excel, PowerPoint, etc. This also means they can't uninstall Skype for Business unless they uninstall all of Office.</span></span>
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a><span data-ttu-id="d5d73-116">選擇是否要讓使用者使用商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="d5d73-116">Choose whether to make Skype for Business available to your users</span></span>

<span data-ttu-id="d5d73-117">做 [為系統管理員](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) ，您可以選擇是否要讓使用者使用商務用 Skype 應用程式。</span><span class="sxs-lookup"><span data-stu-id="d5d73-117">As the [admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) you can choose whether to make the Skype for Business app available to your users.</span></span>
  
- <span data-ttu-id="d5d73-118">**若要控制公司中的** 每個人是否獲得軟體：請登錄 Microsoft 365 系統管理中心，前往安裝我的軟體，然後選取您想要供使用者使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="d5d73-118">**To control whether everyone in your company gets the software**: Sign in to the Microsoft 365 admin center, go to **Install my software**, and then select the software you want to be available for users.</span></span>
    
    ![選擇您想要提供給公司人員的軟體。](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- <span data-ttu-id="d5d73-120">若要控制公司中的特定人員是否取得軟體：請登錄 Microsoft 365 系統管理中心、前往[使用者使用中使用者>、選取要授予軟體存取權限的人，然後按一下 [產品授權旁的編輯>，然後開啟或關閉授權。  >    </span><span class="sxs-lookup"><span data-stu-id="d5d73-120">**To control whether specific people in your company get the software**: Sign in to the Microsoft 365 admin center, go to **Users** > **Active users**, select the person who you want to give access to the software, and then click **Edit** next to **Product licenses** and turn the license on or off.</span></span>
    
    ![選擇您想要使用者存取的軟體。](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> <span data-ttu-id="d5d73-122">如果您需要查看組織中已指派哪些方案給人員，請以使用者活動使用者> **Microsoft** 365 系統  >  **管理中心**。</span><span class="sxs-lookup"><span data-stu-id="d5d73-122">If you need to see what plans are assigned to people in your organization, sign in to the Microsoft 365 admin center > **Users** > **Active users**.</span></span> <span data-ttu-id="d5d73-123">從清單中選取人員，然後查看產品 **授權下的**。</span><span class="sxs-lookup"><span data-stu-id="d5d73-123">Select the person from the list then look under **Product licenses**.</span></span> <span data-ttu-id="d5d73-124">如果您使用的是傳統系統管理中心，請看下指派 **授權**。</span><span class="sxs-lookup"><span data-stu-id="d5d73-124">If you are using the classic admin center, look under **Assigned license**.</span></span> 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a><span data-ttu-id="d5d73-125">手動將商務用 Skype 部署給使用者</span><span class="sxs-lookup"><span data-stu-id="d5d73-125">Manually deploying Skype for Business to your users</span></span>
<span data-ttu-id="d5d73-126"><a name="bkmk_manual_1"> </a></span><span class="sxs-lookup"><span data-stu-id="d5d73-126"><a name="bkmk_manual_1"> </a></span></span>

<span data-ttu-id="d5d73-127">如果您希望使用者從您網路上的位置安裝商務用 Skype 應用程式，而不是從網際網路安裝，您可以下載安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="d5d73-127">If you want your users to install the Skype for Business app from a location on your network instead of from the Internet, you can download the setup files.</span></span> <span data-ttu-id="d5d73-128">若要這麼做，請前往Microsoft 365 系統管理中心的手動部署使用者軟體區段。</span><span class="sxs-lookup"><span data-stu-id="d5d73-128">To do this go to the **Manually deploy user software** section of the Microsoft 365 admin center.</span></span> <span data-ttu-id="d5d73-129">接著，您可以選取安裝 **，** 然後將安裝程式 .exe 檔案儲存到網路位置。</span><span class="sxs-lookup"><span data-stu-id="d5d73-129">You can then select **Install** and save the setup .exe file to a network location.</span></span>
  
<span data-ttu-id="d5d73-130">另一個選項是下載適用于使用者的商務用 Skype Basic 應用程式。</span><span class="sxs-lookup"><span data-stu-id="d5d73-130">Another option is to download the Skype for Business Basic app for your users.</span></span> <span data-ttu-id="d5d73-131">您可以下載[Microsoft 商務用 Skype Basic (32 或 64 位) 。](https://www.microsoft.com/download/details.aspx?id=49440)</span><span class="sxs-lookup"><span data-stu-id="d5d73-131">You can download [Microsoft Skype for Business Basic (32 or 64 Bit)](https://www.microsoft.com/download/details.aspx?id=49440).</span></span>
  
<span data-ttu-id="d5d73-132">針對完整及基本商務用 Skype 應用程式，下載設定檔案之後，您必須手動傳送 (，例如以電子郵件傳送) 網路路徑給使用者，以便使用者執行安裝程式，將應用程式安裝在他們的電腦上。</span><span class="sxs-lookup"><span data-stu-id="d5d73-132">For both the full and basic Skype for Business apps, after you have downloaded the setup files, you will need to manually send (for example, in email) the network path to the users so they can run the setup program to install the app on their computer.</span></span>
  
<span data-ttu-id="d5d73-133">您也可以使用這些下載，使用現有的軟體部署工具和程式，將商務用 Skype 應用程式部署給使用者。</span><span class="sxs-lookup"><span data-stu-id="d5d73-133">You can also use these downloads to deploy the Skype for Business app to your users by using your existing software deployment tools and processes.</span></span>
  
## <a name="for-larger-and-enterprise-organizations"></a><span data-ttu-id="d5d73-134">適用于大型企業及企業組織</span><span class="sxs-lookup"><span data-stu-id="d5d73-134">For larger and enterprise organizations</span></span>

> [!NOTE]
> <span data-ttu-id="d5d73-135">本節僅適用于透過 Office 365 方案提供的商務用 Skype 應用程式。</span><span class="sxs-lookup"><span data-stu-id="d5d73-135">This section only applies to the Skype for Business app available through Office 365 plans.</span></span> <span data-ttu-id="d5d73-136">如果貴組織使用大量授權版的商務用 Skype 應用程式 ，即 Windows Installer 型 (MSI) ，請參閱在商務用 Skype Server 中自訂 Windows 用戶端 [安裝](../../SfbServer/deploy/deploy-clients/customize-windows-client-installation.md)。</span><span class="sxs-lookup"><span data-stu-id="d5d73-136">If your organization is using a volume licensed version of the Skype for Business app, which is Windows Installer-based (MSI), see [Customize Windows client installation in Skype for Business Server](../../SfbServer/deploy/deploy-clients/customize-windows-client-installation.md).</span></span>
  
<span data-ttu-id="d5d73-137">在許多企業或大型組織中，使用者不得在電腦上安裝軟體。</span><span class="sxs-lookup"><span data-stu-id="d5d73-137">In many enterprises or large organizations, users aren't allowed to install software on their computers.</span></span> <span data-ttu-id="d5d73-138">IT 部門會改為將必要的軟體部署到使用者的電腦。</span><span class="sxs-lookup"><span data-stu-id="d5d73-138">Instead, the IT departments deploy the necessary software to the users' computers.</span></span> <span data-ttu-id="d5d73-139">IT 部門也可能想要控制其組織中所使用的網際網路或網路頻寬量，因此他們想要從網路上附近的位置安裝軟體，而不是從網際網路或整個公司網路安裝軟體。</span><span class="sxs-lookup"><span data-stu-id="d5d73-139">IT departments also might want to control the amount of Internet or network bandwidth used in their organization, so they want to install software from a nearby location on their network instead of from across the Internet or across the corporate network.</span></span>
  
<span data-ttu-id="d5d73-140">有了 Office 365，如果您想要控制安裝位置，您有幾個選項可以部署商務用 Skype 應用程式。</span><span class="sxs-lookup"><span data-stu-id="d5d73-140">With Office 365, you have several options for deploying the Skype for Business app if you want to control where it's installed from.</span></span> <span data-ttu-id="d5d73-141">其中一些選項包括下列專案：</span><span class="sxs-lookup"><span data-stu-id="d5d73-141">Some of those options include the following:</span></span>
  
- <span data-ttu-id="d5d73-142">從 Microsoft 365 系統管理中心將商務用 Skype 應用程式下載到您的當地網路，如手動將商務用 [Skype 部署給使用者中所述](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)。</span><span class="sxs-lookup"><span data-stu-id="d5d73-142">Download the Skype for Business app to your local network from the Microsoft 365 admin center, as described in [Manually deploying Skype for Business to your users](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1).</span></span>
    
- <span data-ttu-id="d5d73-143">使用 **[Office 部署工具](https://go.microsoft.com/fwlink/p/?LinkID=626065)** 將 Microsoft 365 企業版 App 或商務用 Skype 應用程式下載至您的當地網路。</span><span class="sxs-lookup"><span data-stu-id="d5d73-143">Use the **[Office Deployment Tool](https://go.microsoft.com/fwlink/p/?LinkID=626065)** to download either Microsoft 365 Apps for enterprise or the Skype for Business app to your local network.</span></span> <span data-ttu-id="d5d73-144">然後，使用 Office 部署工具將應用程式部署到您的使用者。</span><span class="sxs-lookup"><span data-stu-id="d5d73-144">Then, use the Office Deployment Tool to deploy the app to your users.</span></span> <span data-ttu-id="d5d73-145">Office 部署工具讓您能夠控制部署的某些層面，例如語言和版本 (32 位或 64 位) 。</span><span class="sxs-lookup"><span data-stu-id="d5d73-145">The Office Deployment Tool gives you the ability to control certain aspects of the deployment, such as languages and version (32-bit or 64-bit).</span></span>
    
- <span data-ttu-id="d5d73-146">使用現有的軟體部署工具和程式 ，例如 Microsoft 端點組組管理員，將 Microsoft 365 企業版 App 或商務用 Skype 應用程式部署給使用者。</span><span class="sxs-lookup"><span data-stu-id="d5d73-146">Use your existing software deployment tools and processes, such as Microsoft Endpoint Configuration Manager, to deploy Microsoft 365 Apps for enterprise or the Skype for Business app to your users.</span></span> <span data-ttu-id="d5d73-147">您可以在 Office 部署工具或從 Microsoft [](https://go.microsoft.com/fwlink/p/?LinkID=626065) 365 系統管理中心下載的軟體中使用您的現有工具和程式。</span><span class="sxs-lookup"><span data-stu-id="d5d73-147">You can use your existing tools and processes with the [Office Deployment Tool](https://go.microsoft.com/fwlink/p/?LinkID=626065) or with the software that you've downloaded from the Microsoft 365 admin center.</span></span>
    
### <a name="more-info-on-using-the-office-deployment-tool"></a><span data-ttu-id="d5d73-148">有關使用 Office 部署工具之詳細資訊</span><span class="sxs-lookup"><span data-stu-id="d5d73-148">More info on using the Office Deployment Tool</span></span>

<span data-ttu-id="d5d73-149">有關下載 Office 部署工具的詳細資訊，以及安裝商務用 Skype 應用程式和其他 Office 365 用戶端應用程式的詳細資訊，請參閱在 [Office 365](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360)中管理軟體下載設定 。</span><span class="sxs-lookup"><span data-stu-id="d5d73-149">For details on downloading the Office Deployment Tool and more information on installing the Skype for Business app and other Office 365 client apps, see [Manage software download settings in Office 365](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360).</span></span>
  
<span data-ttu-id="d5d73-150">以下是使用 Office 部署工具部署應用程式所涉及步驟概觀：</span><span class="sxs-lookup"><span data-stu-id="d5d73-150">Here's an overview of the steps involved in using the Office Deployment Tool to deploy an app:</span></span>
  
1. <span data-ttu-id="d5d73-151">**[從 Microsoft 下載中心下載](https://www.microsoft.com/download/details.aspx?id=49117)** 最新的 Office 部署工具。</span><span class="sxs-lookup"><span data-stu-id="d5d73-151">**[Download the newest Office Deployment Tool](https://www.microsoft.com/download/details.aspx?id=49117)** from the Microsoft Download Center.</span></span>
    
2. <span data-ttu-id="d5d73-152">建立 configuration.xml 檔案，以用於具有您想要的用戶端應用程式設定之 Office 部署工具，例如設定版本 (32 位或 64 位) 、安裝語言等。</span><span class="sxs-lookup"><span data-stu-id="d5d73-152">Create the configuration.xml file to be used with the Office Deployment Tool that has the client app settings you want, such as setting the version (32-bit or 64-bit), the installation language, etc.</span></span>
    
3. <span data-ttu-id="d5d73-153">使用 Office 部署工具和 configuration.xml檔案，從 Office 內容傳遞網路或 CDN (下載設定檔案至您的) 。</span><span class="sxs-lookup"><span data-stu-id="d5d73-153">Use the Office Deployment Tool and the configuration.xml file to download the setup files to your local or internal network from the Office Content Delivery Network (CDN).</span></span>
    
4. <span data-ttu-id="d5d73-154">使用 Office 部署工具configuration.xml Office 用戶端應用程式 ，包括商務用 Skype 應用程式。</span><span class="sxs-lookup"><span data-stu-id="d5d73-154">Use Office Deployment Tool and the configuration.xml to install the Office client apps, including the Skype for Business app.</span></span>
    
<span data-ttu-id="d5d73-155">有關使用 Office 部署工具及configuration.xml的詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="d5d73-155">For details on using the Office Deployment Tool and configuration.xml file, see the following articles:</span></span>
  
- [<span data-ttu-id="d5d73-156">Office 部署工具概觀</span><span class="sxs-lookup"><span data-stu-id="d5d73-156">Office Deployment Tool overview</span></span>](/deployoffice/overview-office-deployment-tool)
    
- [<span data-ttu-id="d5d73-157">Configuration.xml設定</span><span class="sxs-lookup"><span data-stu-id="d5d73-157">Configuration.xml settings</span></span>](/deployoffice/office-deployment-tool-configuration-options)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="d5d73-158">有關使用 Microsoft 端點組組管理員的更多資訊</span><span class="sxs-lookup"><span data-stu-id="d5d73-158">More info on using Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="d5d73-159">您可以使用現有的軟體部署工具和程式 ，例如 Microsoft 端點組組管理員，來部署商務用 Skype 應用程式。</span><span class="sxs-lookup"><span data-stu-id="d5d73-159">You can use your existing software deployment tools and processes, such as Microsoft Endpoint Configuration Manager, to deploy the Skype for Business app.</span></span> <span data-ttu-id="d5d73-160">您可以在從 Microsoft 365 系統管理中心下載的軟體或 Office 部署工具中，使用這些工具和程式。</span><span class="sxs-lookup"><span data-stu-id="d5d73-160">You can use these tools and processes with either the software that you download from the Microsoft 365 admin center or with the Office Deployment Tool.</span></span>
  
<span data-ttu-id="d5d73-161">若要進一步使用 Configuration Manager 部署軟體，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="d5d73-161">For more information about using Configuration Manager to deploy software, see the following articles:</span></span>
  
- [<span data-ttu-id="d5d73-162">在 Configuration Manager 中建立應用程式</span><span class="sxs-lookup"><span data-stu-id="d5d73-162">Create applications in Configuration Manager</span></span>](/configmgr/apps/deploy-use/create-applications)
    
- [<span data-ttu-id="d5d73-163">使用 Configuration Manager 部署應用程式</span><span class="sxs-lookup"><span data-stu-id="d5d73-163">Deploy applications with Configuration Manager</span></span>](/configmgr/apps/deploy-use/deploy-applications)
    
<span data-ttu-id="d5d73-164">如果您要部署商務用 Skype 應用程式，做為部署企業用 Microsoft 365 App 的一部分，請參閱使用 Configuration Manager 管理企業版 [Microsoft 365 應用程式](/configmgr/sum/deploy-use/manage-office-365-proplus-updates)。</span><span class="sxs-lookup"><span data-stu-id="d5d73-164">If you're deploying the Skype for Business app as part of deploying Microsoft 365 Apps for enterprise, see [Manage Microsoft 365 Apps for enterprise with Configuration Manager](/configmgr/sum/deploy-use/manage-office-365-proplus-updates).</span></span>
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a><span data-ttu-id="d5d73-165">規劃商務用 Skype 應用程式的更新</span><span class="sxs-lookup"><span data-stu-id="d5d73-165">Planning for updates to the Skype for Business app</span></span>

<span data-ttu-id="d5d73-166">在部署商務用 Skype App 時，您必須考慮安裝商務用 Skype 之後，如何取得更新。</span><span class="sxs-lookup"><span data-stu-id="d5d73-166">As part of deploying the Skype for Business app, you need to consider how you want to get updates after Skype for Business is installed.</span></span> <span data-ttu-id="d5d73-167">這些更新可以包含新功能、安全性更新或非安全性更新，例如提供穩定性或改良效果的更新。</span><span class="sxs-lookup"><span data-stu-id="d5d73-167">These updates can include new features, security updates, or non-security updates, such as updates that provide stability or performance improvements.</span></span> <span data-ttu-id="d5d73-168">您需要考慮的兩個主要專案為：</span><span class="sxs-lookup"><span data-stu-id="d5d73-168">The two primary things you need to consider are :</span></span>
  
- <span data-ttu-id="d5d73-169">您想要從何處取得更新</span><span class="sxs-lookup"><span data-stu-id="d5d73-169">Where do you want to get updates from</span></span>
    
- <span data-ttu-id="d5d73-170">您想要取得功能更新的頻次</span><span class="sxs-lookup"><span data-stu-id="d5d73-170">How often do you want to get feature updates</span></span>
    
<span data-ttu-id="d5d73-171">雖然您可以控制從何處取得更新，以及取得功能更新的頻次，但無法選擇您取得的特定安全性更新或非安全性更新。</span><span class="sxs-lookup"><span data-stu-id="d5d73-171">While you can control where you get updates from and how often you get feature updates, you can't choose which specific security updates or non-security updates you get.</span></span>
  
 <span data-ttu-id="d5d73-172">**從何處取得更新**</span><span class="sxs-lookup"><span data-stu-id="d5d73-172">**Where to get updates from**</span></span>
  
<span data-ttu-id="d5d73-173">根據預設，安裝商務用 Skype App 之後，當 Microsoft 提供更新時，系統會自動從網際網路下載更新。</span><span class="sxs-lookup"><span data-stu-id="d5d73-173">By default, after the Skype for Business app is installed, updates will be automatically downloaded from the Internet when they are available from Microsoft.</span></span> <span data-ttu-id="d5d73-174">如果您想要進一控制更新發生的時間，或更新的安裝位置，您可以使用 Office 部署工具或群組原則來設定。</span><span class="sxs-lookup"><span data-stu-id="d5d73-174">If you want more control over when updates occur or where the updates are installed from, you can use the Office Deployment Tool or Group Policy to configure that.</span></span>
  
<span data-ttu-id="d5d73-175">例如，許多組織想要先與一群使用者測試更新，然後再將更新部署到整個組織。</span><span class="sxs-lookup"><span data-stu-id="d5d73-175">For example, many organizations want to test updates with a group of users before deploying them throughout the organization.</span></span> <span data-ttu-id="d5d73-176">您可以使用 Office 部署工具或群組原則來設定商務用 Skype 應用程式，以從您網路上特定位置取得更新，而不是從網際網路自動取得更新，以執行這項操作。</span><span class="sxs-lookup"><span data-stu-id="d5d73-176">You can do this by using the Office Deployment Tool or Group Policy to configure the Skype for Business app to get updates from a specific location on your network, instead of automatically from the Internet.</span></span> <span data-ttu-id="d5d73-177">然後，您可以使用 Office 部署工具每個月將更新下載到您的本地網路。</span><span class="sxs-lookup"><span data-stu-id="d5d73-177">Then, you can use the Office Deployment Tool to download the updates every month to your local network.</span></span>
  
<span data-ttu-id="d5d73-178">有關更新如何適用于 Office 365 軟體之詳細資訊，請參閱以下文章：</span><span class="sxs-lookup"><span data-stu-id="d5d73-178">For more information about how updates work for Office 365 software, see these articles:</span></span>
  
- [<span data-ttu-id="d5d73-179">適用于企業的 Microsoft 365 應用程式更新程式概觀</span><span class="sxs-lookup"><span data-stu-id="d5d73-179">Overview of the update process for Microsoft 365 Apps for enterprise</span></span>](/deployoffice/overview-update-process-microsoft-365-apps)
    
- [<span data-ttu-id="d5d73-180">選擇如何管理適用于企業的 Microsoft 365 應用程式更新</span><span class="sxs-lookup"><span data-stu-id="d5d73-180">Choose how to manage updates to Microsoft 365 Apps for enterprise</span></span>](/deployoffice/choose-how-manage-updates-microsoft-365-apps)
    
- [<span data-ttu-id="d5d73-181">設定適用于企業的 Microsoft 365 應用程式更新設定</span><span class="sxs-lookup"><span data-stu-id="d5d73-181">Configure update settings for Microsoft 365 Apps for enterprise</span></span>](/deployoffice/configure-update-settings-microsoft-365-apps)
    
  <span data-ttu-id="d5d73-182">**取得功能更新的頻次**</span><span class="sxs-lookup"><span data-stu-id="d5d73-182">**How often to get feature updates**</span></span>
  
<span data-ttu-id="d5d73-183">除了從何處取得更新之外，您也可以控制取得商務用 Skype 用戶端新功能的機次。</span><span class="sxs-lookup"><span data-stu-id="d5d73-183">In addition to where you get updates from, you can also control how often you get new features for the Skype for Business client.</span></span> <span data-ttu-id="d5d73-184">這兩個選項如下：</span><span class="sxs-lookup"><span data-stu-id="d5d73-184">The two choices are the following:</span></span>
  
- <span data-ttu-id="d5d73-185">如果有新功能，每個月取得功能更新</span><span class="sxs-lookup"><span data-stu-id="d5d73-185">Get feature updates every month, if there are new features</span></span>
    
- <span data-ttu-id="d5d73-186">每六個月取得功能更新一次</span><span class="sxs-lookup"><span data-stu-id="d5d73-186">Get features updates every six months</span></span>
    
<span data-ttu-id="d5d73-187">對於部分組織，他們想要測試新功能的時間，因此他們只想一年取得兩次功能更新，而不是每個月。</span><span class="sxs-lookup"><span data-stu-id="d5d73-187">For some organizations, they want time to test new features, so they want to get feature updates only twice a year instead of every month.</span></span>
  
<span data-ttu-id="d5d73-188">您可以使用 Office 部署工具或群組原則來設定更新通道，控制取得功能更新的頻次。</span><span class="sxs-lookup"><span data-stu-id="d5d73-188">You can control how often you get feature updates by using the Office Deployment Tool or Group Policy to configure the update channel.</span></span> <span data-ttu-id="d5d73-189">每月通道會提供每月功能更新 (大約) ，而 Semi-Annual通道則每六個月提供一次功能更新。</span><span class="sxs-lookup"><span data-stu-id="d5d73-189">The Monthly Channel gives you feature updates monthly (approximately), while the Semi-Annual Channel gives you feature updates every six months.</span></span> <span data-ttu-id="d5d73-190">有關頻道的資訊，請參閱企業版 [Microsoft 365 應用程式更新通道概觀](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)。</span><span class="sxs-lookup"><span data-stu-id="d5d73-190">For more information about channels, see [Overview of update channels for Microsoft 365 Apps for enterprise](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d5d73-191">相關主題</span><span class="sxs-lookup"><span data-stu-id="d5d73-191">Related topics</span></span>

[<span data-ttu-id="d5d73-192">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="d5d73-192">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="d5d73-193">商務用 Skype 和 Microsoft Teams 附加元件授權</span><span class="sxs-lookup"><span data-stu-id="d5d73-193">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
