---
title: 在商務用 Skype Server 中自訂 Windows 用戶端安裝
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: '摘要: 商務用 Skype 的安裝方法與工具概覽。'
ms.openlocfilehash: 40e5b9145f06038e76aee0b77b287e6dce9a8b3b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191143"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a><span data-ttu-id="febe5-103">在商務用 Skype Server 中自訂 Windows 用戶端安裝</span><span class="sxs-lookup"><span data-stu-id="febe5-103">Customize Windows client installation in Skype for Business Server</span></span>
 
<span data-ttu-id="febe5-104">**摘要:** 商務用 Skype 的安裝方法與工具概覽。</span><span class="sxs-lookup"><span data-stu-id="febe5-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="febe5-105">如需 Office 365 隨附之商務用 Skype 的安裝資訊, 請參閱[在 office 365 中部署商務用 skype 用戶端](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)。</span><span class="sxs-lookup"><span data-stu-id="febe5-105">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="febe5-106">企業系統管理員可以使用本節中討論的方法, 來自訂以 Windows 安裝程式為基礎的商務用 Skype 版本 (.msi)。</span><span class="sxs-lookup"><span data-stu-id="febe5-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="febe5-107">因為沒有任何單一工具提供所有的自訂選項, 所以您可以在商務用 Skype 部署中使用這些方法的組合。</span><span class="sxs-lookup"><span data-stu-id="febe5-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="febe5-108">您可能會使用下列各節所述的工具:</span><span class="sxs-lookup"><span data-stu-id="febe5-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="febe5-109">[在商務用 Skype Server 中使用 Office 自訂工具 (OCT)](use-the-office-customization-tool-oct.md) , 來自訂商務用 skype 和其他 Office 程式的設定選項和功能。</span><span class="sxs-lookup"><span data-stu-id="febe5-109">[Use the Office Customization Tool (OCT) in Skype for Business Server](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="febe5-110">[在商務用 Skype Server 中使用 config.xml 來執行安裝](use-config-xml-to-perform-installation-tasks.md)工作, 以指定網路安裝點的路徑, 並執行緘默安裝。</span><span class="sxs-lookup"><span data-stu-id="febe5-110">[Use Config.xml to perform installation tasks in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="febe5-111">[在商務用 Skype Server 中使用 Setup 命令列選項](use-setup-command-line-options.md), 以指定要在安裝期間使用的 config.xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="febe5-111">[Use Setup command-line options in Skype for Business Server](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="febe5-112">使用 [群組原則物件編輯器] MMC 管理單元,[在商務用 Skype Server 中設定用戶端引導原則](configure-client-bootstrapping-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="febe5-112">[Configure client bootstrapping policies in Skype for Business Server](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="febe5-113">在您部署 Office 產品套件時, 您可能會想要設定其他的選項。</span><span class="sxs-lookup"><span data-stu-id="febe5-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="febe5-114">本節中的主題概述這些自訂工具, 並討論商務用 Skype 所專用的考慮。</span><span class="sxs-lookup"><span data-stu-id="febe5-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="febe5-115">[隨附] 是每個工具的詳細 Office 說明的連結。</span><span class="sxs-lookup"><span data-stu-id="febe5-115">Included are links to detailed Office help for each tool.</span></span> 
  

