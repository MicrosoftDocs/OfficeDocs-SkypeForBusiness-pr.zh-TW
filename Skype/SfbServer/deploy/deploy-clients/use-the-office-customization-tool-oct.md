---
title: '在商務用 Skype Server 中使用 Office 自訂工具 (OCT) '
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
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 摘要：如何搭配商務用 Skype 用戶端使用 Office 自訂工具。
ms.openlocfilehash: 32cd7951690ce5b1e38c20d83c8f53a9c48cd19c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100449"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a><span data-ttu-id="b1092-103">在商務用 Skype Server 中使用 Office 自訂工具 (OCT) </span><span class="sxs-lookup"><span data-stu-id="b1092-103">Use the Office Customization Tool (OCT) in Skype for Business Server</span></span>
 
<span data-ttu-id="b1092-104">**摘要：** 如何搭配商務用 Skype 用戶端使用 Office 自訂工具。</span><span class="sxs-lookup"><span data-stu-id="b1092-104">**Summary:** How to use the Office Customization Tool with the Skype for Business client.</span></span>
  
<span data-ttu-id="b1092-105">Office 自訂工具 (OCT) 屬於安裝程式的一部分，也是許多自訂的建議使用工具。</span><span class="sxs-lookup"><span data-stu-id="b1092-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="b1092-106">您可以使用 OCT 自訂 Office，並將自訂儲存在安裝程式自訂 .msp 檔案中。</span><span class="sxs-lookup"><span data-stu-id="b1092-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="b1092-107">您將此檔案放在網路安裝點上的 Updates 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="b1092-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="b1092-108">當您安裝 Office 時，安裝程式會在 Updates 資料夾中尋找安裝程式自訂檔案，並套用自訂。</span><span class="sxs-lookup"><span data-stu-id="b1092-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="b1092-109">「更新」資料夾只可用於在 Office 的初始安裝期間部署軟體更新。</span><span class="sxs-lookup"><span data-stu-id="b1092-109">The Updates folder can be used only to deploy software updates during an initial installation of Office.</span></span>
  
<span data-ttu-id="b1092-110">OCT 是安裝程式的一部分，只用于大量授權版本的產品。</span><span class="sxs-lookup"><span data-stu-id="b1092-110">The OCT is part of setup and it is only used for volume licensed versions of the product.</span></span> <span data-ttu-id="b1092-111">您可以  `setup.exe /admin` 從包含 Office 來源檔案之網路安裝點的根目錄輸入命令列，以執行 OCT。</span><span class="sxs-lookup"><span data-stu-id="b1092-111">You run the OCT by typing  `setup.exe /admin` at the command line from the root of the network installation point that contains the Office source files.</span></span> <span data-ttu-id="b1092-112">例如，使用下列程式：</span><span class="sxs-lookup"><span data-stu-id="b1092-112">For example, use the following:</span></span>
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
<span data-ttu-id="b1092-113">管理員使用 OCT 建立安裝程式自訂 .msp 檔案，並可自訂下欄區域：</span><span class="sxs-lookup"><span data-stu-id="b1092-113">Administrators use the OCT to create a setup customization .msp file and can customize the following areas:</span></span>
  
- <span data-ttu-id="b1092-114">**安裝程式** 用於指定用戶端的預設安裝位置和預設組織名稱、其他網路安裝來源、產品金鑰、使用者授權合約、顯示層級、要移除的舊版 Office、要在安裝期間執行的自訂程式、安全性設定，以及安裝程式屬性。</span><span class="sxs-lookup"><span data-stu-id="b1092-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>
    
- <span data-ttu-id="b1092-115">**功能** 用來設定使用者設定，以及自訂安裝 Office 功能的方式。</span><span class="sxs-lookup"><span data-stu-id="b1092-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="b1092-116">系統管理員可以使用 OCT 為使用者指定 Office 應用程式設定的初始預設值。</span><span class="sxs-lookup"><span data-stu-id="b1092-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="b1092-117">使用者可以在安裝之後修改大部分的設定。</span><span class="sxs-lookup"><span data-stu-id="b1092-117">Users can modify most of the settings after the installation.</span></span>
    
- <span data-ttu-id="b1092-118">**其他內容** 用於新增或移除檔案、新增或移除登錄專案，以及設定快捷方式。</span><span class="sxs-lookup"><span data-stu-id="b1092-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>
    
- <span data-ttu-id="b1092-119">**Outlook** 用來自訂使用者的預設 Outlook 設定檔、指定 Exchange 設定、新增帳戶、移除帳戶和匯出設定，以及指定傳送/接收群組。</span><span class="sxs-lookup"><span data-stu-id="b1092-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\Receive groups.</span></span>
    
<span data-ttu-id="b1092-120">如需 OCT 的詳細資訊，請參閱 [使用 oct 自訂 Office 2013](/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15))。</span><span class="sxs-lookup"><span data-stu-id="b1092-120">For information about the OCT, see [Use the OCT to customize Office 2013](/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span></span> <span data-ttu-id="b1092-121">請注意，此資訊也適用于更新版本的 Office。</span><span class="sxs-lookup"><span data-stu-id="b1092-121">Note that this information also applies to later versions of Office.</span></span>
