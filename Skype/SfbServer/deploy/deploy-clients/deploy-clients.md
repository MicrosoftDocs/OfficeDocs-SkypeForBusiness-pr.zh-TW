---
title: 針對商務用 Skype Server 部署用戶端
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
description: 摘要：商務用 Skype 的企業用戶端安裝方法概覽。
ms.openlocfilehash: 0e7859fe207ed80aa7dceef794aa57d15cc0c79b
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768726"
---
# <a name="deploy-clients-for-skype-for-business-server"></a><span data-ttu-id="263cc-103">針對商務用 Skype Server 部署用戶端</span><span class="sxs-lookup"><span data-stu-id="263cc-103">Deploy clients for Skype for Business Server</span></span>
 
<span data-ttu-id="263cc-104">**摘要：** 商務用 Skype 的企業用戶端安裝方法概覽。</span><span class="sxs-lookup"><span data-stu-id="263cc-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="263cc-105">如何將商務用 Skype 部署到您的使用者，取決於您是否已購買商務用 skype 作為 Office 365 方案的一部分，或是您購買了大量授權版的商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="263cc-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="263cc-106">**Office 365**如果您有包含商務用 Skype 的 Office 365 方案，則所使用的安裝技術稱為「隨選即用」。</span><span class="sxs-lookup"><span data-stu-id="263cc-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="263cc-107">有了 Office 365，您就可以讓使用者從 Office 365 入口網站自行安裝商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="263cc-107">With Office 365, you can let your users install Skype for Business for themselves from the Office 365 portal.</span></span> <span data-ttu-id="263cc-108">或者，您可以將軟體下載到您的本機網路，然後使用您現有的軟體部署工具（例如 Microsoft 端點建構管理員），將商務用 Skype 部署到您的使用者。</span><span class="sxs-lookup"><span data-stu-id="263cc-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="263cc-109">如需 Office 365 隨附之商務用 Skype 的安裝資訊，請參閱[在 office 365 中部署商務用 skype 用戶端](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)。</span><span class="sxs-lookup"><span data-stu-id="263cc-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="263cc-110">**大量授權**如果您有大量授權版的商務用 Skype 2015 或2016用戶端，則使用的安裝技術是 Windows Installer （MSI）。</span><span class="sxs-lookup"><span data-stu-id="263cc-110">**Volume licensed** If you have a volume licensed version of the Skype for Business 2015 or 2016 client, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="263cc-111">以 Windows 安裝程式為基礎的安裝套件由多個 MSI 檔案組成。</span><span class="sxs-lookup"><span data-stu-id="263cc-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="263cc-112">語言中立的核心 MSI 套件與一或多個語言特定套件結合，以製作完整的產品。</span><span class="sxs-lookup"><span data-stu-id="263cc-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="263cc-113">安裝程式會彙編個別套件，並在安裝使用者電腦上的 Office 期間和之後執行自訂及維護作業。</span><span class="sxs-lookup"><span data-stu-id="263cc-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="263cc-114">商務用 Skype 2019 用戶端使用「隨選即用」的安裝程式。</span><span class="sxs-lookup"><span data-stu-id="263cc-114">The Skype for Business 2019 client uses Click-to-Run installers.</span></span>
    
<span data-ttu-id="263cc-115">本節中的主題說明如何使用及自訂 Windows 安裝程式，以透過您的一般程式將商務用 Skype 用戶端部署到您的使用者。</span><span class="sxs-lookup"><span data-stu-id="263cc-115">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="263cc-116">Microsoft Office 的 Skype 會議增益集（支援 Outlook 訊息和共同作業用戶端中的會議管理）會自動安裝與商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="263cc-116">The Skype Meeting Add-in for Microsoft Office, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="263cc-117">Office 365 安裝程式不會卸載舊版的 Lync。</span><span class="sxs-lookup"><span data-stu-id="263cc-117">The Office 365 setup program does not uninstall previous versions of Lync.</span></span> <span data-ttu-id="263cc-118">商務用 Skype 用戶端會與其他 Lync 用戶端並排安裝。</span><span class="sxs-lookup"><span data-stu-id="263cc-118">The Skype for Business client installs side-by-side with other Lync clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="263cc-119">安裝 Windows 用戶端</span><span class="sxs-lookup"><span data-stu-id="263cc-119">Installing Windows clients</span></span>

- [<span data-ttu-id="263cc-120">在商務用 Skype Server 中自訂 Windows 用戶端安裝</span><span class="sxs-lookup"><span data-stu-id="263cc-120">Customize Windows client installation in Skype for Business Server</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="263cc-121">透過商務用 Skype 設定用戶端體驗</span><span class="sxs-lookup"><span data-stu-id="263cc-121">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="263cc-122">在商務用 Skype Server 中設定智慧連絡人清單</span><span class="sxs-lookup"><span data-stu-id="263cc-122">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="263cc-123">安裝裝置用戶端</span><span class="sxs-lookup"><span data-stu-id="263cc-123">Installing device clients</span></span>

- [<span data-ttu-id="263cc-124">安裝並測試 Windows Phone 版商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="263cc-124">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="263cc-125">安裝並測試 iOS 版商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="263cc-125">Install and test Skype for Business for iOS</span></span>](ios.md)
    
    
- [<span data-ttu-id="263cc-126">使用商務用 Skype Server 部署 Lync VDI 外掛程式</span><span class="sxs-lookup"><span data-stu-id="263cc-126">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="263cc-127">在商務用 Skype Server 中部署網頁下載用戶端</span><span class="sxs-lookup"><span data-stu-id="263cc-127">Deploy Web downloadable clients in Skype for Business Server</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="263cc-128">在商務用 Skype 中自訂 Mac 用戶端體驗</span><span class="sxs-lookup"><span data-stu-id="263cc-128">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="263cc-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="263cc-129">See also</span></span>

[<span data-ttu-id="263cc-130">在 Office 365 中部署商務用 Skype 用戶端</span><span class="sxs-lookup"><span data-stu-id="263cc-130">Deploy the Skype for Business client in Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
