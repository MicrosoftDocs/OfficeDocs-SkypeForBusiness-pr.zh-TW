---
title: Export-CcConfigurationSampleFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: Export-CcConfigurationSampleFile Cmdlet 會將商務用 Skype 雲端連接器版本範例設定檔 (.ini) 匯出到雲端連接器裝置的裝置目錄。 您可以修改並重新命名檔案, 以用於您的部署。
ms.openlocfilehash: 440253bc6b9c4e980a6f7ac4aae0c82ebad05660
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190801"
---
# <a name="export-ccconfigurationsamplefile"></a><span data-ttu-id="848e7-104">Export-CcConfigurationSampleFile</span><span class="sxs-lookup"><span data-stu-id="848e7-104">Export-CcConfigurationSampleFile</span></span>
 
<span data-ttu-id="848e7-105">Export-CcConfigurationSampleFile Cmdlet 會將商務用 Skype 雲端連接器版本範例設定檔 (.ini) 匯出到雲端連接器裝置的裝置目錄。</span><span class="sxs-lookup"><span data-stu-id="848e7-105">The Export-CcConfigurationSampleFile cmdlet exports a Skype for Business Cloud Connector Edition sample configuration file (.ini) to the appliance directory of a Cloud Connector appliance.</span></span> <span data-ttu-id="848e7-106">您可以修改並重新命名檔案, 以用於您的部署。</span><span class="sxs-lookup"><span data-stu-id="848e7-106">You can modify and rename the file to use for your deployment.</span></span>
  
<span data-ttu-id="848e7-107">此 Cmdlet 適用于商務用 Skype 雲端連接器 Edition 1.4.1, 1.4.2。</span><span class="sxs-lookup"><span data-stu-id="848e7-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a><span data-ttu-id="848e7-108">參數</span><span class="sxs-lookup"><span data-stu-id="848e7-108">Parameters</span></span>

<span data-ttu-id="848e7-109">無</span><span class="sxs-lookup"><span data-stu-id="848e7-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="848e7-110">範例</span><span class="sxs-lookup"><span data-stu-id="848e7-110">Examples</span></span>
<span data-ttu-id="848e7-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="848e7-111"></span></span>

### <a name="example-1"></a><span data-ttu-id="848e7-112">範例 1</span><span class="sxs-lookup"><span data-stu-id="848e7-112">Example 1</span></span>

<span data-ttu-id="848e7-113">下列範例會從 Microsoft 網站下載範例設定檔, 並將它寫入雲端連接器裝置的裝置目錄:</span><span class="sxs-lookup"><span data-stu-id="848e7-113">The following example downloads a sample configuration file from the Microsoft site and writes it to the appliance directory of the Cloud Connector appliance:</span></span>
  
```
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a><span data-ttu-id="848e7-114">詳細描述</span><span class="sxs-lookup"><span data-stu-id="848e7-114">Detailed Description</span></span>
<span data-ttu-id="848e7-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="848e7-115"></span></span>

<span data-ttu-id="848e7-116">目前的雲端連接器版本需要您在 .ini 檔案中提供數個參數;例如, 參數 (例如雲端連接器元件的虛擬機器 IP 位址、元件名稱、閘道參數等)。</span><span class="sxs-lookup"><span data-stu-id="848e7-116">The current version of Cloud Connector requires you to provide several parameters in the .ini file; for example, parameters such as the IP addresses of virtual machines for the Cloud Connector components, component names, gateway parameters, and so on.</span></span>
  
<span data-ttu-id="848e7-117">這個 Cmdlet 是在雲端連接器的主機電腦上執行時, 從 Microsoft 網站下載含配置範例的示範 .ini 檔案。</span><span class="sxs-lookup"><span data-stu-id="848e7-117">This cmdlet, when run on the host machine of Cloud Connector, downloads a sample .ini file with configuration examples from the Microsoft site.</span></span> <span data-ttu-id="848e7-118">這個 Cmdlet 會將檔案寫入雲端連接器裝置的裝置目錄中。</span><span class="sxs-lookup"><span data-stu-id="848e7-118">The cmdlet writes the file to the appliance directory of the Cloud Connector appliance.</span></span> <span data-ttu-id="848e7-119">裝置目錄是使用 CcApplianceDirectory Cmdlet 來指定。</span><span class="sxs-lookup"><span data-stu-id="848e7-119">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="848e7-120">輸入類型</span><span class="sxs-lookup"><span data-stu-id="848e7-120">Input Types</span></span>
<span data-ttu-id="848e7-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="848e7-121"></span></span>

<span data-ttu-id="848e7-122">無。</span><span class="sxs-lookup"><span data-stu-id="848e7-122">None.</span></span> <span data-ttu-id="848e7-123">Export CcConfigurationSampleFile Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="848e7-123">The Export-CcConfigurationSampleFile cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="848e7-124">傳回類型</span><span class="sxs-lookup"><span data-stu-id="848e7-124">Return Types</span></span>
<span data-ttu-id="848e7-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="848e7-125"></span></span>

<span data-ttu-id="848e7-126">無</span><span class="sxs-lookup"><span data-stu-id="848e7-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="848e7-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="848e7-127">See also</span></span>
<span data-ttu-id="848e7-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="848e7-128"></span></span>

[<span data-ttu-id="848e7-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="848e7-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

