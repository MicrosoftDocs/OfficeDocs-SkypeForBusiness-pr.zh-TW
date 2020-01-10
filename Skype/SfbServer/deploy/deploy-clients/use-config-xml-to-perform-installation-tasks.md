---
title: 在商務用 Skype 用戶端中使用 Config.xml 執行安裝工作
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 摘要：如何使用 Config.xml 檔案來指定其他安裝指示。
ms.openlocfilehash: d561e4f6e3213ae7dff160b9b43e02f26ecc0522
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002933"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a><span data-ttu-id="934df-103">在商務用 Skype 用戶端中使用 Config.xml 執行安裝工作</span><span class="sxs-lookup"><span data-stu-id="934df-103">Use Config.xml to perform installation tasks in Skype for Business clients</span></span>

<span data-ttu-id="934df-104">**摘要：** 如何使用 Config.xml 檔案來指定其他安裝指示。</span><span class="sxs-lookup"><span data-stu-id="934df-104">**Summary:** How to use the Config.xml file to specify additional installation instructions.</span></span>

<span data-ttu-id="934df-105">雖然 Office 自訂工具（OCT）是自訂安裝的主要工具，但系統管理員可以使用 Config.xml 檔案來指定不在 OCT 中提供的其他安裝指示。</span><span class="sxs-lookup"><span data-stu-id="934df-105">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT.</span></span> <span data-ttu-id="934df-106">下列自訂功能只能使用 Config.xml 檔案來進行：</span><span class="sxs-lookup"><span data-stu-id="934df-106">The following customizations can only be made by using the Config.xml file:</span></span>

- <span data-ttu-id="934df-107">指定網路安裝點的路徑。</span><span class="sxs-lookup"><span data-stu-id="934df-107">Specify the path of the network installation point.</span></span>

- <span data-ttu-id="934df-108">選取要安裝的產品。</span><span class="sxs-lookup"><span data-stu-id="934df-108">Select the products to install.</span></span>

- <span data-ttu-id="934df-109">設定記錄，以及安裝程式自訂檔案和軟體更新的位置。</span><span class="sxs-lookup"><span data-stu-id="934df-109">Configure logging and the location of the Setup customization file and software updates.</span></span>

- <span data-ttu-id="934df-110">指定安裝選項，例如 [使用者名稱]。</span><span class="sxs-lookup"><span data-stu-id="934df-110">Specify installation options, such as user name.</span></span>

- <span data-ttu-id="934df-111">將本機安裝來源（.LIS）複製到使用者的電腦，但不安裝 Office。</span><span class="sxs-lookup"><span data-stu-id="934df-111">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>

- <span data-ttu-id="934df-112">新增或移除安裝的語言。</span><span class="sxs-lookup"><span data-stu-id="934df-112">Add or remove languages from the installation.</span></span>

<span data-ttu-id="934df-113">建議您使用 Config.xml 檔案來設定商務用 Skype 無訊息安裝。</span><span class="sxs-lookup"><span data-stu-id="934df-113">We recommend that you use the Config.xml file to configure Skype for Business silent installation.</span></span> 

<span data-ttu-id="934df-114">根據預設，儲存在核心產品資料夾中的 Config.xml 檔案（例如，[_產品_]）。WW）指示安裝程式安裝該產品。</span><span class="sxs-lookup"><span data-stu-id="934df-114">By default, the Config.xml file that is stored in the core product folder (for example, \ _product_.WW) directs Setup to install that product.</span></span> <span data-ttu-id="934df-115">例如，下列資料夾中的 Config.xml 檔案會安裝商務用 Skype：</span><span class="sxs-lookup"><span data-stu-id="934df-115">For example, the Config.xml file in the following folder installs Skype for Business:</span></span>

- <span data-ttu-id="934df-116">\\server\share\Skype15\Skype.WW \Config.xml</span><span class="sxs-lookup"><span data-stu-id="934df-116">\\server\share\Skype15\Skype.WW \Config.xml</span></span>

<span data-ttu-id="934df-117">下表列出最常用於商務用 Skype 安裝的 Config .xml 元素。</span><span class="sxs-lookup"><span data-stu-id="934df-117">The Config.xml elements most commonly used for Skype for Business installation are listed in the following table.</span></span>

<span data-ttu-id="934df-118">**Config .xml 元素**</span><span class="sxs-lookup"><span data-stu-id="934df-118">**Config.xml elements**</span></span>


| <span data-ttu-id="934df-119">**元件**</span><span class="sxs-lookup"><span data-stu-id="934df-119">**Element**</span></span>              | <span data-ttu-id="934df-120">**描述**</span><span class="sxs-lookup"><span data-stu-id="934df-120">**Description**</span></span>                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="934df-121">Configuration</span><span class="sxs-lookup"><span data-stu-id="934df-121">Configuration</span></span>  <br/>     | <span data-ttu-id="934df-122">高層元素（必要）。</span><span class="sxs-lookup"><span data-stu-id="934df-122">Top-level element (required).</span></span> <span data-ttu-id="934df-123">包含 Product 屬性，例如： Product = Lync （這適用于商務用 Skype 用戶端）</span><span class="sxs-lookup"><span data-stu-id="934df-123">Contains the Product attribute, for example: Product=Lync (This will work for Skype for Business clients)</span></span>  <br/>                                                                                                                                                          |
| <span data-ttu-id="934df-124">OptionState</span><span class="sxs-lookup"><span data-stu-id="934df-124">OptionState</span></span>  <br/>       | <span data-ttu-id="934df-125">指定安裝期間特定產品功能的處理方式。</span><span class="sxs-lookup"><span data-stu-id="934df-125">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="934df-126">使用下列屬性來避免安裝 Business Connectivity Service，其中包含會干擾 Outlook 的共用元件：</span><span class="sxs-lookup"><span data-stu-id="934df-126">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook:</span></span> <br/>  <span data-ttu-id="934df-127">識別碼 = "LOBiMain"</span><span class="sxs-lookup"><span data-stu-id="934df-127">Id="LOBiMain"</span></span> <br/>  <span data-ttu-id="934df-128">State = "不存在"</span><span class="sxs-lookup"><span data-stu-id="934df-128">State="Absent"</span></span> <br/>  <span data-ttu-id="934df-129">子級 = "Force"</span><span class="sxs-lookup"><span data-stu-id="934df-129">Children="Force"</span></span> <br/> |
| <span data-ttu-id="934df-130">顯示幕</span><span class="sxs-lookup"><span data-stu-id="934df-130">Display</span></span>  <br/>           | <span data-ttu-id="934df-131">安裝程式顯示給使用者的 UI 層級。</span><span class="sxs-lookup"><span data-stu-id="934df-131">The level of UI that Setup displays to the user.</span></span> <span data-ttu-id="934df-132">一般屬性包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="934df-132">Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="934df-133">CompletionNotice = "Yes"</span><span class="sxs-lookup"><span data-stu-id="934df-133">CompletionNotice="Yes"</span></span>                                                                                                                                                                                |
| <span data-ttu-id="934df-134">記錄</span><span class="sxs-lookup"><span data-stu-id="934df-134">Logging</span></span>  <br/>           | <span data-ttu-id="934df-135">安裝程式所執行之記錄類型的選項。</span><span class="sxs-lookup"><span data-stu-id="934df-135">Options for the kind of logging that Setup performs.</span></span> <span data-ttu-id="934df-136">一般屬性包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="934df-136">Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="934df-137">輸入 = "Off"</span><span class="sxs-lookup"><span data-stu-id="934df-137">Type ="Off"</span></span>                                                                                                                                                                                       |
| <span data-ttu-id="934df-138">正在</span><span class="sxs-lookup"><span data-stu-id="934df-138">Setting</span></span>  <br/>           | <span data-ttu-id="934df-139">指定 Windows 安裝程式屬性的值。</span><span class="sxs-lookup"><span data-stu-id="934df-139">Specifies values for Windows Installer properties.</span></span> <span data-ttu-id="934df-140">一般屬性包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="934df-140">Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="934df-141">設定識別碼 = " *name*" （Windows Installer 屬性的名稱）</span><span class="sxs-lookup"><span data-stu-id="934df-141">Setting Id=" *name*" (the name of the Windows Installer property)</span></span>  <br/>  <span data-ttu-id="934df-142">Value = " *value*" （要指派給屬性的值）</span><span class="sxs-lookup"><span data-stu-id="934df-142">Value=" *value*" (the value to assign to the property)</span></span>  <br/>                                                             |
| <span data-ttu-id="934df-143">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="934df-143">DistributionPoint</span></span>  <br/> | <span data-ttu-id="934df-144">要執行安裝的網路安裝點的完整路徑。</span><span class="sxs-lookup"><span data-stu-id="934df-144">The fully qualified path of the network installation point from which the installation is to run.</span></span> <span data-ttu-id="934df-145">包括 Location 屬性：</span><span class="sxs-lookup"><span data-stu-id="934df-145">Includes the Location attribute:</span></span> <br/>  <span data-ttu-id="934df-146">位置 = " *path*"</span><span class="sxs-lookup"><span data-stu-id="934df-146">Location=" *path*"</span></span>  <br/>                                                                                                                                     |

<span data-ttu-id="934df-147">下列範例顯示商務用 Skype 用戶端的典型無訊息安裝的 Config.xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="934df-147">The following example shows a Config.xml file for a typical silent installation of the Skype for Business client.</span></span> 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

<span data-ttu-id="934df-148">有關使用 Config.xml 檔案來執行 Office 安裝與維護工作的詳細資訊，請參閱[https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514)。</span><span class="sxs-lookup"><span data-stu-id="934df-148">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).</span></span>

## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="934df-149">自訂 Config.xml 檔案</span><span class="sxs-lookup"><span data-stu-id="934df-149">To customize the Config.xml file</span></span>

1. <span data-ttu-id="934df-150">使用文字編輯器工具（例如記事本）來開啟 Config.xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="934df-150">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>

2. <span data-ttu-id="934df-151">找出包含您要變更之元素的線條。</span><span class="sxs-lookup"><span data-stu-id="934df-151">Locate the lines that contain the elements you want to change.</span></span>

3. <span data-ttu-id="934df-152">使用您要使用的緘默選項來修改元素專案。</span><span class="sxs-lookup"><span data-stu-id="934df-152">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="934df-153">請務必移除批註分隔符號 "\<!--" 和 "--\>"。</span><span class="sxs-lookup"><span data-stu-id="934df-153">Make sure that you remove the comment delimiters, "\<!--" and "--\>".</span></span> <span data-ttu-id="934df-154">例如，使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="934df-154">For example, use the following syntax:</span></span>

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. <span data-ttu-id="934df-155">儲存 Config.xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="934df-155">Save the Config.xml file.</span></span>


