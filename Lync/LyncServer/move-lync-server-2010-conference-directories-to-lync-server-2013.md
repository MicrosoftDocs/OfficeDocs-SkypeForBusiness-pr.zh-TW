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
ms.openlocfilehash: 6712e22ffcdc2eaea9ae39be961bb50316beed5b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a><span data-ttu-id="37910-102">移動會議目錄</span><span class="sxs-lookup"><span data-stu-id="37910-102">Move Conference Directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37910-103">_**上次修改主題：** 2014年-05-28_</span><span class="sxs-lookup"><span data-stu-id="37910-103">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="37910-104">解除委任集區之前您必須針對每個會議目錄執行下列程序 Lync Server 2010 集區中。</span><span class="sxs-lookup"><span data-stu-id="37910-104">Before decommissioning a pool you must perform the following procedure for each conference directory in your Lync Server 2010 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="37910-105">若要將會議目錄移至 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37910-105">To Move a Conference Directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="37910-106">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="37910-106">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="37910-107">若要取得您的組織中會議目錄的身分識別，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="37910-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="37910-108">上述命令會傳回您組織中的所有會議目錄。</span><span class="sxs-lookup"><span data-stu-id="37910-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="37910-109">因此，您可能想要限制結果，以解除委任集區。</span><span class="sxs-lookup"><span data-stu-id="37910-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="37910-110">比方說，如果您打算解除委任集區與完整的網域名稱 (FQDN) pool01.contoso.net，使用此命令來限制傳回的資料會議目錄從該集區：</span><span class="sxs-lookup"><span data-stu-id="37910-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="37910-111">該命令會傳回會議目錄 ServiceID 屬性包含 FQDN pool01.contoso.net 的位置。</span><span class="sxs-lookup"><span data-stu-id="37910-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="37910-112">若要移動會議目錄，請執行下列命令以取得每個會議目錄集區中：</span><span class="sxs-lookup"><span data-stu-id="37910-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="37910-113">例如，若要移動會議目錄 3，請使用此命令中，指定為 TargetPool 的 Lync Server 2013 集區：</span><span class="sxs-lookup"><span data-stu-id="37910-113">For example, to move conference directory 3 use this command, specifying a Lync Server 2013 pool as the TargetPool:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    <span data-ttu-id="37910-114">如果您想要移動的集區上的所有會議目錄，然後使用類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="37910-114">If you want to move all the conference directories on a pool then use a command similar to the following:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

<span data-ttu-id="37910-115">請參閱 「 解除安裝 Microsoft Lync Server 2010 及移除伺服器角色 」 的文件 (這可以從下載[http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)) 如需在解除委任 Lync 2010 集區的完整、 逐步指示。</span><span class="sxs-lookup"><span data-stu-id="37910-115">Please see the document "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles" (which can be downloaded from [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)) for comprehensive, step-by-step instructions on decommissioning Lync 2010 pools.</span></span>

<span data-ttu-id="37910-116">移動會議目錄時您可能會發生下列錯誤：</span><span class="sxs-lookup"><span data-stu-id="37910-116">When moving conference directories you might encounter the following error:</span></span>

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

<span data-ttu-id="37910-117">Lync Server 管理命令介面需要更新的組 Active Directory 權限，才能完成工作時，通常就會發生此錯誤。</span><span class="sxs-lookup"><span data-stu-id="37910-117">This error typically occurs when the Lync Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="37910-118">若要解決此問題，請關閉目前的執行個體的管理命令介面中，然後開啟命令介面的新執行個體並重新執行命令以將會議目錄移。</span><span class="sxs-lookup"><span data-stu-id="37910-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command in order to move the conference directory.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

