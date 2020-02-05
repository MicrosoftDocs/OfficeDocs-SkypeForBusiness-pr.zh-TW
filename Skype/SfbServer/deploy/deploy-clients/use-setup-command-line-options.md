---
title: 在商務用 Skype 用戶端使用 Setup 命令列選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 摘要：瞭解 Office 設定中的 setup.exe 命令列操作。
ms.openlocfilehash: 68add6e2744e9648db49508519c14e64b4e6aeef
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768626"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a><span data-ttu-id="1b043-103">在商務用 Skype 用戶端使用 Setup 命令列選項</span><span class="sxs-lookup"><span data-stu-id="1b043-103">Use Setup command-line options with Skype for Business clients</span></span>
 
<span data-ttu-id="1b043-104">**摘要：** 瞭解 Office 設定中的 setup.exe 命令列操作。</span><span class="sxs-lookup"><span data-stu-id="1b043-104">**Summary:** Learn about Setup.exe command line operations in Office setup.</span></span>
  
<span data-ttu-id="1b043-105">Setup.exe 命令列適用于 Office 設定中的極少作業。</span><span class="sxs-lookup"><span data-stu-id="1b043-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="1b043-106">您通常會使用 Office 自訂工具和 Config.xml 檔案來進行產品設定和功能自訂，而不是使用 [設定] 命令列選項。</span><span class="sxs-lookup"><span data-stu-id="1b043-106">Instead of using the Setup command-line options, you'll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>
  
<span data-ttu-id="1b043-107">Office Setup.exe 命令列會辨識下表所述的命令列選項。</span><span class="sxs-lookup"><span data-stu-id="1b043-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>
  
<span data-ttu-id="1b043-108">**Office 設定命令列選項**</span><span class="sxs-lookup"><span data-stu-id="1b043-108">**Office Setup Command-Line Options**</span></span>

|<span data-ttu-id="1b043-109">**設定命令列選項**</span><span class="sxs-lookup"><span data-stu-id="1b043-109">**Setup Command-Line Option**</span></span>|<span data-ttu-id="1b043-110">**說明**</span><span class="sxs-lookup"><span data-stu-id="1b043-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1b043-111">/admin</span><span class="sxs-lookup"><span data-stu-id="1b043-111">/admin</span></span>  <br/> |<span data-ttu-id="1b043-112">執行 Office 自訂工具來建立安裝程式自訂檔（.msp 檔案）。</span><span class="sxs-lookup"><span data-stu-id="1b043-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span>  <br/> |
|<span data-ttu-id="1b043-113">/adminfile [path]</span><span class="sxs-lookup"><span data-stu-id="1b043-113">/adminfile [path]</span></span>  <br/> |<span data-ttu-id="1b043-114">將指定的安裝程式自訂檔案套用到安裝。</span><span class="sxs-lookup"><span data-stu-id="1b043-114">Applies the specified Setup customization file to the installation.</span></span> <span data-ttu-id="1b043-115">您可以指定特定自訂檔案（.msp 檔案）或儲存自訂檔案的資料夾路徑。</span><span class="sxs-lookup"><span data-stu-id="1b043-115">You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span>  <br/> |
|<span data-ttu-id="1b043-116">/config [path]</span><span class="sxs-lookup"><span data-stu-id="1b043-116">/config [path]</span></span>  <br/> |<span data-ttu-id="1b043-117">指定安裝程式在安裝期間使用的 Config.xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="1b043-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="1b043-118">使用/config 選項指定您針對商務用 Skype 安裝所自訂的 Config.xml 檔案，例如：`/config \\server\share\Skype15\Skype.WW\Config.xml`</span><span class="sxs-lookup"><span data-stu-id="1b043-118">Use the /config option to specify the Config.xml file you customized for Skype for Business installations, for example:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span></span> <br/> |
|<span data-ttu-id="1b043-119">/modify Skype</span><span class="sxs-lookup"><span data-stu-id="1b043-119">/modify Skype</span></span>  <br/> |<span data-ttu-id="1b043-120">與已修改的 Config.xml 檔案搭配使用，可在維護模式中執行安裝程式，並變更現有的 Office 安裝。</span><span class="sxs-lookup"><span data-stu-id="1b043-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="1b043-121">例如，您可以使用/modify 選項來新增或移除商務用 Skype 功能。</span><span class="sxs-lookup"><span data-stu-id="1b043-121">For example, you can use the /modify option to add or remove Skype for Business features.</span></span>  <br/> |
|<span data-ttu-id="1b043-122">/repair Skype</span><span class="sxs-lookup"><span data-stu-id="1b043-122">/repair Skype</span></span>  <br/> |<span data-ttu-id="1b043-123">從使用者的電腦執行安裝程式，以修復商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="1b043-123">Runs Setup from the user's computer to repair Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="1b043-124">/uninstall Skype</span><span class="sxs-lookup"><span data-stu-id="1b043-124">/uninstall Skype</span></span>  <br/> |<span data-ttu-id="1b043-125">執行安裝程式，從使用者的電腦中移除商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="1b043-125">Runs Setup to remove Skype for Business from the user's computer.</span></span>  <br/> |
   


