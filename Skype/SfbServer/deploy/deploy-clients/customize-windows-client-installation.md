---
title: 在商務用 Skype Server 中自訂 Windows 用戶端安裝
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: 摘要：商務用 Skype 的安裝方法與工具概述。
ms.openlocfilehash: 001224369e46978e96ee063b31fcb546ef213a05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805713"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a><span data-ttu-id="4578b-103">在商務用 Skype Server 中自訂 Windows 用戶端安裝</span><span class="sxs-lookup"><span data-stu-id="4578b-103">Customize Windows client installation in Skype for Business Server</span></span>
 
<span data-ttu-id="4578b-104">**摘要：** 商務用 Skype 之安裝方法及工具的概述。</span><span class="sxs-lookup"><span data-stu-id="4578b-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4578b-105">如需 Microsoft 365 和 Office 365 隨附的商務用 Skype 相關安裝資訊，請參閱 [在 microsoft 365 或 office 365 中部署商務用 skype 用戶端](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)。</span><span class="sxs-lookup"><span data-stu-id="4578b-105">For installation information about Skype for Business that comes with Microsoft 365 and Office 365, see [Deploy the Skype for Business client in Microsoft 365 or Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="4578b-106">企業系統管理員可以使用本節所述的方法，來自訂 Windows Installer 型 ( .msi) 安裝商務用 Skype 的大量授權版本。</span><span class="sxs-lookup"><span data-stu-id="4578b-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="4578b-107">由於沒有單一工具提供所有自訂選項，因此您可能會在商務用 Skype 部署中使用這些方法的組合。</span><span class="sxs-lookup"><span data-stu-id="4578b-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="4578b-108">您可以使用下列各節所述的工具：</span><span class="sxs-lookup"><span data-stu-id="4578b-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="4578b-109">[使用 Office 自訂工具 (OCT) 在商務用 Skype Server 中](use-the-office-customization-tool-oct.md) ，為商務用 skype 和其他 Office 程式自訂安裝選項及功能。</span><span class="sxs-lookup"><span data-stu-id="4578b-109">[Use the Office Customization Tool (OCT) in Skype for Business Server](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="4578b-110">[使用 Config.xml 在商務用 Skype Server 中執行安裝工作](use-config-xml-to-perform-installation-tasks.md) ，以指定網路安裝點的路徑，並執行無訊息安裝。</span><span class="sxs-lookup"><span data-stu-id="4578b-110">[Use Config.xml to perform installation tasks in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="4578b-111">[使用商務用 Skype Server 中的安裝程式命令列選項](use-setup-command-line-options.md) ，指定要在安裝期間使用的 Config.xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="4578b-111">[Use Setup command-line options in Skype for Business Server](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="4578b-112">使用群組原則物件編輯器 MMC 嵌入式管理單元，[在商務用 Skype Server 中設定用戶端引導原則](configure-client-bootstrapping-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="4578b-112">[Configure client bootstrapping policies in Skype for Business Server](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="4578b-113">當您部署 Office 產品套件時，可能會有其他的選項可供您設定。</span><span class="sxs-lookup"><span data-stu-id="4578b-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="4578b-114">本節中的主題會概括介紹這些自訂工具，並討論商務用 Skype 所特有的考慮。</span><span class="sxs-lookup"><span data-stu-id="4578b-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="4578b-115">包含的連結為每個工具的詳細 Office 說明。</span><span class="sxs-lookup"><span data-stu-id="4578b-115">Included are links to detailed Office help for each tool.</span></span> 
  

