---
title: 將 Lync Server 2010 會議目錄移至 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move Conference Directories
ms:assetid: 659867e0-ce91-4a95-9787-b1c1566460a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727126(v=OCS.15)
ms:contentKeyID: 62387565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9bd597665f389c814fbdc8fe1745587fd3d1b3e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766114"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a><span data-ttu-id="29185-102">移動會議目錄</span><span class="sxs-lookup"><span data-stu-id="29185-102">Move Conference Directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29185-103">_**主題上次修改日期：** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="29185-103">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="29185-104">在解除池的授權前，您必須針對 Lync Server 2010 池中的每個會議目錄執行下列程式。</span><span class="sxs-lookup"><span data-stu-id="29185-104">Before decommissioning a pool you must perform the following procedure for each conference directory in your Lync Server 2010 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="29185-105">將會議目錄移至 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29185-105">To Move a Conference Directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="29185-106">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="29185-106">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="29185-107">若要取得貴組織中會議目錄的身分識別，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="29185-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="29185-108">上述命令會傳回貴組織中的所有會議目錄。</span><span class="sxs-lookup"><span data-stu-id="29185-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="29185-109">因此，您可能會想要將結果限制在已解除授權的池中。</span><span class="sxs-lookup"><span data-stu-id="29185-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="29185-110">例如，如果您是使用完整的功能變數名稱（FQDN） pool01.contoso.net 來解除池，請使用此命令，將傳回的資料限制在該池中的會議目錄：</span><span class="sxs-lookup"><span data-stu-id="29185-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="29185-111">該命令只會傳回 ServiceID 屬性包含 FQDN pool01.contoso.net 的會議目錄。</span><span class="sxs-lookup"><span data-stu-id="29185-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="29185-112">若要移動會議目錄，請針對池中的每個會議目錄執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="29185-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="29185-113">例如，若要移動會議目錄3，請使用此命令，並將 Lync Server 2013 池指定為 TargetPool：</span><span class="sxs-lookup"><span data-stu-id="29185-113">For example, to move conference directory 3 use this command, specifying a Lync Server 2013 pool as the TargetPool:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    <span data-ttu-id="29185-114">如果您想要移動一個資源池中的所有會議目錄，請使用類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="29185-114">If you want to move all the conference directories on a pool then use a command similar to the following:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

<span data-ttu-id="29185-115">如需有關解除授權 Lync 2010 池的完整、逐步指示，請參閱檔「卸載 Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)Server 2010 並移除伺服器角色」（可供下載）。</span><span class="sxs-lookup"><span data-stu-id="29185-115">Please see the document "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles" (which can be downloaded from [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)) for comprehensive, step-by-step instructions on decommissioning Lync 2010 pools.</span></span>

<span data-ttu-id="29185-116">移動會議目錄時，您可能會遇到下列錯誤：</span><span class="sxs-lookup"><span data-stu-id="29185-116">When moving conference directories you might encounter the following error:</span></span>

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

<span data-ttu-id="29185-117">當 Lync Server 管理命令介面需要更新的 Active Directory 許可權集才能完成工作時，通常會發生此錯誤。</span><span class="sxs-lookup"><span data-stu-id="29185-117">This error typically occurs when the Lync Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="29185-118">若要解決此問題，請關閉目前的管理命令介面實例，然後開啟一個新的 Shell 實例，然後重新執行命令，以移動會議目錄。</span><span class="sxs-lookup"><span data-stu-id="29185-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command in order to move the conference directory.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

