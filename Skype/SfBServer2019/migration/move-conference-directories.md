---
title: 移動會議目錄
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 在解除池的授權前，您必須針對舊版池中的每個會議目錄執行下列程式。
ms.openlocfilehash: bdcb816a91f6bc4a4372141595e46ba2369618a6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813281"
---
# <a name="move-conference-directories"></a><span data-ttu-id="32094-103">移動會議目錄</span><span class="sxs-lookup"><span data-stu-id="32094-103">Move Conference Directories</span></span>

<span data-ttu-id="32094-104">在解除池的授權前，您必須針對舊版池中的每個會議目錄執行下列程式。</span><span class="sxs-lookup"><span data-stu-id="32094-104">Before decommissioning a pool, you must perform the following procedure for each conference directory in your legacy pool.</span></span>
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a><span data-ttu-id="32094-105">將會議目錄移至商務用 Skype Server 2019</span><span class="sxs-lookup"><span data-stu-id="32094-105">To Move a Conference Directory to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="32094-106">開啟商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="32094-106">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="32094-107">若要取得貴組織中會議目錄的身分識別，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="32094-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    <span data-ttu-id="32094-108">上述命令會傳回貴組織中的所有會議目錄。</span><span class="sxs-lookup"><span data-stu-id="32094-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="32094-109">因此，您可能會想要將結果限制在已解除授權的池中。</span><span class="sxs-lookup"><span data-stu-id="32094-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="32094-110">例如，如果您是使用完整的功能變數名稱（FQDN） pool01.contoso.net 來解除池，請使用此命令，將傳回的資料限制在該池中的會議目錄：</span><span class="sxs-lookup"><span data-stu-id="32094-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    <span data-ttu-id="32094-111">該命令只會傳回 ServiceID 屬性包含 FQDN pool01.contoso.net 的會議目錄。</span><span class="sxs-lookup"><span data-stu-id="32094-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>
    
3. <span data-ttu-id="32094-112">若要移動會議目錄，請針對池中的每個會議目錄執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="32094-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    <span data-ttu-id="32094-113">例如，若要移動會議目錄3，請使用此命令，將商務用 Skype Server 2019 池指定為 TargetPool：</span><span class="sxs-lookup"><span data-stu-id="32094-113">For example, to move conference directory 3, use this command, specifying a Skype for Business Server 2019 pool as the TargetPool:</span></span>
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    <span data-ttu-id="32094-114">如果您想要移動一個池上的所有會議目錄，請使用類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="32094-114">If you want to move all the conference directories on a pool, use a command similar to the following:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

<span data-ttu-id="32094-115">下載[Microsoft 舊版並移除伺服器角色](https://go.microsoft.com/fwlink/p/?linkId=246227)，以取得有關解除授權舊版池的完整逐步指示。</span><span class="sxs-lookup"><span data-stu-id="32094-115">Download [Uninstalling Microsoft legacy and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227) for comprehensive, step-by-step instructions on decommissioning legacy pools.</span></span>
  
<span data-ttu-id="32094-116">移動會議目錄時，您可能會遇到下列錯誤：</span><span class="sxs-lookup"><span data-stu-id="32094-116">When moving conference directories, you might encounter the following error:</span></span>
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

<span data-ttu-id="32094-117">如果商務用 Skype 伺服器管理命令介面需要更新的 Active Directory 許可權集才能完成工作，通常會發生此錯誤。</span><span class="sxs-lookup"><span data-stu-id="32094-117">This error typically occurs when the Skype for Business Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="32094-118">若要解決此問題，請關閉目前的管理命令介面實例，然後開啟一個新的 Shell 實例，然後重新執行該命令來移動會議目錄。</span><span class="sxs-lookup"><span data-stu-id="32094-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command to move the conference directory.</span></span>
  

