---
title: 在商務用 Skype 用戶端中使用 Config.xml 執行安裝工作
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 摘要：如何使用 Config.xml 檔案指定其他安裝指示。
ms.openlocfilehash: 1b8aeeb16e061e7816e475f01c9cd9a9146306ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825183"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a><span data-ttu-id="5a1e1-103">在商務用 Skype 用戶端中使用 Config.xml 執行安裝工作</span><span class="sxs-lookup"><span data-stu-id="5a1e1-103">Use Config.xml to perform installation tasks in Skype for Business clients</span></span>

<span data-ttu-id="5a1e1-104">**摘要：** 如何使用 Config.xml 檔案指定其他安裝指示。</span><span class="sxs-lookup"><span data-stu-id="5a1e1-104">**Summary:** How to use the Config.xml file to specify additional installation instructions.</span></span>

<span data-ttu-id="5a1e1-p101">雖然 Office 自訂工具 (OCT) 是自訂安裝的主要工具，但是系統管理員可以使用 Config.xml 檔案來指定 OCT 中所沒有的其他安裝指示。下列自訂只能使用 Config.xml 檔案來進行：</span><span class="sxs-lookup"><span data-stu-id="5a1e1-p101">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT. The following customizations can only be made by using the Config.xml file:</span></span>

- <span data-ttu-id="5a1e1-107">指定網路安裝點的路徑。</span><span class="sxs-lookup"><span data-stu-id="5a1e1-107">Specify the path of the network installation point.</span></span>

- <span data-ttu-id="5a1e1-108">選取所要安裝的產品。</span><span class="sxs-lookup"><span data-stu-id="5a1e1-108">Select the products to install.</span></span>

- <span data-ttu-id="5a1e1-109">設定安裝程式自訂檔案和軟體更新的記錄及位置。</span><span class="sxs-lookup"><span data-stu-id="5a1e1-109">Configure logging and the location of the Setup customization file and software updates.</span></span>

- <span data-ttu-id="5a1e1-110">指定安裝選項，例如使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="5a1e1-110">Specify installation options, such as user name.</span></span>

- <span data-ttu-id="5a1e1-111">將本機安裝來源 (LIS) 複製到使用者的電腦，而不安裝 Office。</span><span class="sxs-lookup"><span data-stu-id="5a1e1-111">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>

- <span data-ttu-id="5a1e1-112">在安裝中新增或移除語言。</span><span class="sxs-lookup"><span data-stu-id="5a1e1-112">Add or remove languages from the installation.</span></span>

<span data-ttu-id="5a1e1-113">建議您使用 Config.xml 檔案來設定商務用 Skype 無訊息安裝。</span><span class="sxs-lookup"><span data-stu-id="5a1e1-113">We recommend that you use the Config.xml file to configure Skype for Business silent installation.</span></span> 

<span data-ttu-id="5a1e1-114">根據預設，儲存在核心產品資料夾中的 Config.xml 檔案 (例如，- _product_。WW) 指示安裝程式安裝該產品。</span><span class="sxs-lookup"><span data-stu-id="5a1e1-114">By default, the Config.xml file that is stored in the core product folder (for example, \ _product_.WW) directs Setup to install that product.</span></span> <span data-ttu-id="5a1e1-115">例如，下列資料夾中的 Config.xml 檔會安裝商務用 Skype：</span><span class="sxs-lookup"><span data-stu-id="5a1e1-115">For example, the Config.xml file in the following folder installs Skype for Business:</span></span>

- <span data-ttu-id="5a1e1-116">\\server\share\Skype15\Skype.WW \Config.xml</span><span class="sxs-lookup"><span data-stu-id="5a1e1-116">\\server\share\Skype15\Skype.WW \Config.xml</span></span>

<span data-ttu-id="5a1e1-117">下表列出最常用於商務用 Skype 安裝的 Config.xml 元素。</span><span class="sxs-lookup"><span data-stu-id="5a1e1-117">The Config.xml elements most commonly used for Skype for Business installation are listed in the following table.</span></span>

<span data-ttu-id="5a1e1-118">**Config.xml 元素**</span><span class="sxs-lookup"><span data-stu-id="5a1e1-118">**Config.xml elements**</span></span>


| <span data-ttu-id="5a1e1-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="5a1e1-119">**Element**</span></span>              | <span data-ttu-id="5a1e1-120">**描述**</span><span class="sxs-lookup"><span data-stu-id="5a1e1-120">**Description**</span></span>                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="5a1e1-121">組態</span><span class="sxs-lookup"><span data-stu-id="5a1e1-121">Configuration</span></span>  <br/>     | <span data-ttu-id="5a1e1-122">最上層元素 (必要)。</span><span class="sxs-lookup"><span data-stu-id="5a1e1-122">Top-level element (required).</span></span> <span data-ttu-id="5a1e1-123">包含 Product 屬性，例如： Product = Lync (此功能會針對商務用 Skype 用戶端運作) </span><span class="sxs-lookup"><span data-stu-id="5a1e1-123">Contains the Product attribute, for example: Product=Lync (This will work for Skype for Business clients)</span></span>  <br/>                                                                                                                                                          |
| <span data-ttu-id="5a1e1-124">OptionState</span><span class="sxs-lookup"><span data-stu-id="5a1e1-124">OptionState</span></span>  <br/>       | <span data-ttu-id="5a1e1-125">指定在安裝期間如何處理特定的產品功能。</span><span class="sxs-lookup"><span data-stu-id="5a1e1-125">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="5a1e1-126">使用下列屬性可防止安裝 Business Connectivity Services，其中包含干擾 Outlook 的共用元件：</span><span class="sxs-lookup"><span data-stu-id="5a1e1-126">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook:</span></span> <br/>  <span data-ttu-id="5a1e1-127">識別碼 = "LOBiMain"</span><span class="sxs-lookup"><span data-stu-id="5a1e1-127">Id="LOBiMain"</span></span> <br/>  <span data-ttu-id="5a1e1-128">State = "不存在"</span><span class="sxs-lookup"><span data-stu-id="5a1e1-128">State="Absent"</span></span> <br/>  <span data-ttu-id="5a1e1-129">子系 = "Force"</span><span class="sxs-lookup"><span data-stu-id="5a1e1-129">Children="Force"</span></span> <br/> |
| <span data-ttu-id="5a1e1-130">顯示器</span><span class="sxs-lookup"><span data-stu-id="5a1e1-130">Display</span></span>  <br/>           | <span data-ttu-id="5a1e1-p105">安裝程式向使用者顯示的 UI 層級。一般屬性包括：</span><span class="sxs-lookup"><span data-stu-id="5a1e1-p105">The level of UI that Setup displays to the user. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="5a1e1-133">CompletionNotice= "Yes"</span><span class="sxs-lookup"><span data-stu-id="5a1e1-133">CompletionNotice="Yes"</span></span>                                                                                                                                                                                |
| <span data-ttu-id="5a1e1-134">記錄</span><span class="sxs-lookup"><span data-stu-id="5a1e1-134">Logging</span></span>  <br/>           | <span data-ttu-id="5a1e1-p106">安裝程式執行之記錄類型的選項。一般屬性包括：</span><span class="sxs-lookup"><span data-stu-id="5a1e1-p106">Options for the kind of logging that Setup performs. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="5a1e1-137">Type = "Off"</span><span class="sxs-lookup"><span data-stu-id="5a1e1-137">Type ="Off"</span></span>                                                                                                                                                                                       |
| <span data-ttu-id="5a1e1-138">設定</span><span class="sxs-lookup"><span data-stu-id="5a1e1-138">Setting</span></span>  <br/>           | <span data-ttu-id="5a1e1-p107">指定 Windows Installer 內容的值。一般屬性包括：</span><span class="sxs-lookup"><span data-stu-id="5a1e1-p107">Specifies values for Windows Installer properties. Typical attributes include the following: </span></span><br/>  <span data-ttu-id="5a1e1-141">設定識別碼 = " *name*" (Windows Installer 屬性的名稱) </span><span class="sxs-lookup"><span data-stu-id="5a1e1-141">Setting Id=" *name*" (the name of the Windows Installer property)</span></span>  <br/>  <span data-ttu-id="5a1e1-142">Value = " *value*" (要指派給屬性的值) </span><span class="sxs-lookup"><span data-stu-id="5a1e1-142">Value=" *value*" (the value to assign to the property)</span></span>  <br/>                                                             |
| <span data-ttu-id="5a1e1-143">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="5a1e1-143">DistributionPoint</span></span>  <br/> | <span data-ttu-id="5a1e1-p108">要執行安裝之網路安裝點的完整路徑。包括 Location 屬性：</span><span class="sxs-lookup"><span data-stu-id="5a1e1-p108">The fully qualified path of the network installation point from which the installation is to run. Includes the Location attribute: </span></span><br/>  <span data-ttu-id="5a1e1-146">Location = " *path*"</span><span class="sxs-lookup"><span data-stu-id="5a1e1-146">Location=" *path*"</span></span>  <br/>                                                                                                                                     |

<span data-ttu-id="5a1e1-147">下列範例顯示商務用 Skype 用戶端一般無訊息安裝的 Config.xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="5a1e1-147">The following example shows a Config.xml file for a typical silent installation of the Skype for Business client.</span></span> 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

<span data-ttu-id="5a1e1-148">您可以在使用 Config.xml 檔案執行 Office 安裝及維護工作的詳細資訊 [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514) 。</span><span class="sxs-lookup"><span data-stu-id="5a1e1-148">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).</span></span>

## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="5a1e1-149">自訂 Config.xml 檔案</span><span class="sxs-lookup"><span data-stu-id="5a1e1-149">To customize the Config.xml file</span></span>

1. <span data-ttu-id="5a1e1-150">使用文字編輯器工具來開啟 Config.xml 檔案，例如 [記事本]。</span><span class="sxs-lookup"><span data-stu-id="5a1e1-150">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>

2. <span data-ttu-id="5a1e1-151">找到包含您要變更之元素的那幾行。</span><span class="sxs-lookup"><span data-stu-id="5a1e1-151">Locate the lines that contain the elements you want to change.</span></span>

3. <span data-ttu-id="5a1e1-152">以您要使用的無訊息選項來修改元素項目。</span><span class="sxs-lookup"><span data-stu-id="5a1e1-152">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="5a1e1-153">請務必移除批註定界符 " \<!--" and "--\> "。</span><span class="sxs-lookup"><span data-stu-id="5a1e1-153">Make sure that you remove the comment delimiters, "\<!--" and "--\>".</span></span> <span data-ttu-id="5a1e1-154">例如，使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="5a1e1-154">For example, use the following syntax:</span></span>

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. <span data-ttu-id="5a1e1-155">儲存 Config.xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="5a1e1-155">Save the Config.xml file.</span></span>


