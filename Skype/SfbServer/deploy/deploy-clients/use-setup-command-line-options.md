---
title: 搭配商務用 Skype 用戶端使用安裝程式命令列選項
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
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 摘要：瞭解 Office 安裝中的 Setup.exe 命令列作業。
ms.openlocfilehash: 042ba2bdea6228f7c8a726c0bdb2ca5c3233d5f4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837203"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a><span data-ttu-id="cac6f-103">搭配商務用 Skype 用戶端使用安裝程式命令列選項</span><span class="sxs-lookup"><span data-stu-id="cac6f-103">Use Setup command-line options with Skype for Business clients</span></span>
 
<span data-ttu-id="cac6f-104">**摘要：** 深入瞭解 Office 安裝中的 Setup.exe 命令列作業。</span><span class="sxs-lookup"><span data-stu-id="cac6f-104">**Summary:** Learn about Setup.exe command line operations in Office setup.</span></span>
  
<span data-ttu-id="cac6f-105">Setup.exe 命令列將用於 Office 安裝中非常少的作業。</span><span class="sxs-lookup"><span data-stu-id="cac6f-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="cac6f-106">您通常會使用 Office 自訂工具和 Config.xml 檔案進行產品安裝和功能自訂，而不是使用安裝程式的命令列選項。</span><span class="sxs-lookup"><span data-stu-id="cac6f-106">Instead of using the Setup command-line options, you'll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>
  
<span data-ttu-id="cac6f-107">Office Setup.exe 命令列會識別下表所述的命令列選項。</span><span class="sxs-lookup"><span data-stu-id="cac6f-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>
  
<span data-ttu-id="cac6f-108">**Office 安裝程式 Command-Line 選項**</span><span class="sxs-lookup"><span data-stu-id="cac6f-108">**Office Setup Command-Line Options**</span></span>

|<span data-ttu-id="cac6f-109">**安裝 Command-Line 選項**</span><span class="sxs-lookup"><span data-stu-id="cac6f-109">**Setup Command-Line Option**</span></span>|<span data-ttu-id="cac6f-110">**描述**</span><span class="sxs-lookup"><span data-stu-id="cac6f-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cac6f-111">/admin</span><span class="sxs-lookup"><span data-stu-id="cac6f-111">/admin</span></span>  <br/> |<span data-ttu-id="cac6f-112">執行 Office 自訂工具，以建立安裝程式自訂檔案 (.msp 檔案)。</span><span class="sxs-lookup"><span data-stu-id="cac6f-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span>  <br/> |
|<span data-ttu-id="cac6f-113">/adminfile [path]</span><span class="sxs-lookup"><span data-stu-id="cac6f-113">/adminfile [path]</span></span>  <br/> |<span data-ttu-id="cac6f-p102">將指定的安裝程式自訂檔案套用至安裝。您可以指定特定自訂檔案 (.msp 檔案) 的路徑，或是儲存自訂檔案的資料夾路徑。</span><span class="sxs-lookup"><span data-stu-id="cac6f-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span>  <br/> |
|<span data-ttu-id="cac6f-116">/config [path]</span><span class="sxs-lookup"><span data-stu-id="cac6f-116">/config [path]</span></span>  <br/> |<span data-ttu-id="cac6f-117">指定在安裝過程中，安裝程式所使用的 Config.xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="cac6f-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="cac6f-118">使用 [/config] 選項指定您為商務用 Skype 安裝所自訂的 Config.xml 檔案，例如：  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span><span class="sxs-lookup"><span data-stu-id="cac6f-118">Use the /config option to specify the Config.xml file you customized for Skype for Business installations, for example:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span></span> <br/> |
|<span data-ttu-id="cac6f-119">/modify Skype</span><span class="sxs-lookup"><span data-stu-id="cac6f-119">/modify Skype</span></span>  <br/> |<span data-ttu-id="cac6f-120">與修改的 Config.xml 檔案搭配使用，即可在維護模式中執行安裝程式，並對現有的 Office 安裝進行變更。</span><span class="sxs-lookup"><span data-stu-id="cac6f-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="cac6f-121">例如，您可以使用/modify 選項來新增或移除商務用 Skype 功能。</span><span class="sxs-lookup"><span data-stu-id="cac6f-121">For example, you can use the /modify option to add or remove Skype for Business features.</span></span>  <br/> |
|<span data-ttu-id="cac6f-122">/repair Skype</span><span class="sxs-lookup"><span data-stu-id="cac6f-122">/repair Skype</span></span>  <br/> |<span data-ttu-id="cac6f-123">從使用者的電腦執行安裝程式，以修理商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="cac6f-123">Runs Setup from the user's computer to repair Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="cac6f-124">/uninstall Skype</span><span class="sxs-lookup"><span data-stu-id="cac6f-124">/uninstall Skype</span></span>  <br/> |<span data-ttu-id="cac6f-125">執行安裝程式以從使用者的電腦中移除商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="cac6f-125">Runs Setup to remove Skype for Business from the user's computer.</span></span>  <br/> |
   


