---
title: 為商務用 Skype Server 部署用戶端
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 摘要：商務用 Skype 的企業用戶端安裝方法的概述。
ms.openlocfilehash: 8d6e59582c3c420d5752a84f793e6c3025b3c500
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220643"
---
# <a name="deploy-clients-for-skype-for-business-server"></a><span data-ttu-id="c8e0a-103">為商務用 Skype Server 部署用戶端</span><span class="sxs-lookup"><span data-stu-id="c8e0a-103">Deploy clients for Skype for Business Server</span></span>
 
<span data-ttu-id="c8e0a-104">**摘要：** 商務用 Skype 之企業用戶端安裝方法的概述。</span><span class="sxs-lookup"><span data-stu-id="c8e0a-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="c8e0a-105">如何將商務用 Skype 部署至使用者，取決於您購買的商務用 skype 是否為 Microsoft 365 或 Office 365 方案的一部分，或是您購買的商務用 Skype 的大量授權版本。</span><span class="sxs-lookup"><span data-stu-id="c8e0a-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of a Microsoft 365 or Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="c8e0a-106">**Microsoft 365 或 Office 365**如果您有包含商務用 Skype 的 Microsoft 365 或 Office 365 方案，則使用的安裝技術稱為 Click-to-Run。</span><span class="sxs-lookup"><span data-stu-id="c8e0a-106">**Microsoft 365 or Office 365** If you have a Microsoft 365 or Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="c8e0a-107">您可以讓您的使用者自行從 Microsoft 365 系統管理中心安裝商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="c8e0a-107">You can let your users install Skype for Business for themselves from the Microsoft 365 admin center.</span></span> <span data-ttu-id="c8e0a-108">或者，您可以將軟體下載到您的本機網路，然後使用您現有的軟體部署工具，例如 Microsoft 端點 Configuration Manager，將商務用 Skype 部署至使用者。</span><span class="sxs-lookup"><span data-stu-id="c8e0a-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="c8e0a-109">如需 Microsoft 365 和 Office 365 隨附的商務用 Skype 相關安裝資訊，請參閱[在 microsoft 365 或 office 365 中部署商務用 skype 用戶端](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)。</span><span class="sxs-lookup"><span data-stu-id="c8e0a-109">For installation information about Skype for Business that comes with Microsoft 365 and Office 365, see [Deploy the Skype for Business client in Microsoft 365 or Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="c8e0a-110">**大量授權**如果您有大量授權版本的商務用 Skype 2015 或2016用戶端，則使用的安裝技術為 Windows Installer （MSI）。</span><span class="sxs-lookup"><span data-stu-id="c8e0a-110">**Volume licensed** If you have a volume licensed version of the Skype for Business 2015 or 2016 client, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="c8e0a-111">Windows Installer 型安裝套件是由多個 MSI 檔案所組成。</span><span class="sxs-lookup"><span data-stu-id="c8e0a-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="c8e0a-112">中性語言核心 MSI 套件結合了一或多個特定語言套件，組成完整的產品。</span><span class="sxs-lookup"><span data-stu-id="c8e0a-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="c8e0a-113">安裝程式組合了個別套件，在安裝 Office 於使用者的電腦期間 (以及之後)，執行自訂與維護工作。</span><span class="sxs-lookup"><span data-stu-id="c8e0a-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="c8e0a-114">商務用 Skype 2019 用戶端使用 Click-to-Run 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="c8e0a-114">The Skype for Business 2019 client uses Click-to-Run installers.</span></span>
    
<span data-ttu-id="c8e0a-115">本節中的主題說明如何使用和自訂 Windows 安裝程式，透過您的一般程式，將商務用 Skype 用戶端部署至使用者。</span><span class="sxs-lookup"><span data-stu-id="c8e0a-115">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c8e0a-116">Microsoft Office 的 Skype 會議增益集（支援 Outlook 郵件和共同作業用戶端中的會議管理）會自動安裝商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="c8e0a-116">The Skype Meeting Add-in for Microsoft Office, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c8e0a-117">Microsoft 365 和 Office 365 安裝程式不會卸載舊版的 Lync。</span><span class="sxs-lookup"><span data-stu-id="c8e0a-117">The Microsoft 365 and Office 365 setup programs don't uninstall previous versions of Lync.</span></span> <span data-ttu-id="c8e0a-118">商務用 Skype 用戶端會與其他 Lync 用戶端同時安裝。</span><span class="sxs-lookup"><span data-stu-id="c8e0a-118">The Skype for Business client installs side-by-side with other Lync clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="c8e0a-119">安裝 Windows 用戶端</span><span class="sxs-lookup"><span data-stu-id="c8e0a-119">Installing Windows clients</span></span>

- [<span data-ttu-id="c8e0a-120">在商務用 Skype Server 中自訂 Windows 用戶端安裝</span><span class="sxs-lookup"><span data-stu-id="c8e0a-120">Customize Windows client installation in Skype for Business Server</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="c8e0a-121">使用商務用 Skype 設定用戶端經驗</span><span class="sxs-lookup"><span data-stu-id="c8e0a-121">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="c8e0a-122">在商務用 Skype Server 中設定智慧連絡人清單</span><span class="sxs-lookup"><span data-stu-id="c8e0a-122">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="c8e0a-123">安裝裝置用戶端</span><span class="sxs-lookup"><span data-stu-id="c8e0a-123">Installing device clients</span></span>

- [<span data-ttu-id="c8e0a-124">安裝並測試適用于 Windows Phone 的商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="c8e0a-124">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="c8e0a-125">安裝及測試 iOS 的商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="c8e0a-125">Install and test Skype for Business for iOS</span></span>](ios.md)
    
    
- [<span data-ttu-id="c8e0a-126">使用商務用 Skype Server 部署 Lync VDI 外掛程式</span><span class="sxs-lookup"><span data-stu-id="c8e0a-126">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="c8e0a-127">在商務用 Skype Server 中部署 Web 可下載的用戶端</span><span class="sxs-lookup"><span data-stu-id="c8e0a-127">Deploy Web downloadable clients in Skype for Business Server</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="c8e0a-128">在商務用 Skype 中自訂 Mac 用戶端體驗</span><span class="sxs-lookup"><span data-stu-id="c8e0a-128">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="c8e0a-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c8e0a-129">See also</span></span>

[<span data-ttu-id="c8e0a-130">在 Microsoft 365 或 Office 365 中部署商務用 Skype 用戶端</span><span class="sxs-lookup"><span data-stu-id="c8e0a-130">Deploy the Skype for Business client in Microsoft 365 or Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
