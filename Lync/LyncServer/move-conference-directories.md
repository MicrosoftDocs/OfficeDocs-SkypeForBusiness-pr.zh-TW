---
title: 移動會議目錄
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d53e3183d781f527373ffcfb8573da9fbb52d41f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500300"
---
# <a name="move-conference-directories"></a><span data-ttu-id="36533-102">移動會議目錄</span><span class="sxs-lookup"><span data-stu-id="36533-102">Move conference directories</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36533-103">_**主題上次修改日期：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="36533-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="36533-104">在解除委任集區之前，您必須針對 Office 通訊伺服器 2007 R2 集區中的每個會議目錄執行下列程式。</span><span class="sxs-lookup"><span data-stu-id="36533-104">Before decommissioning a pool, you need to perform the following procedure for each conference directory in your Office Communications Server 2007 R2 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="36533-105">將會議目錄移至 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36533-105">To move a conference directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="36533-106">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="36533-106">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="36533-107">若要取得組織中會議目錄的身分識別，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="36533-107">To obtain the identity of the conference directories in your organization, run the following commands:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="36533-p101">由於此 Cmdlet 會傳回組織中的所有會議目錄，所以您可能會想要將結果僅限於您要解除委任的集區。例如，如果您想要解除委任完整網域名稱 (FQDN) 為 pool01.contoso.net 的集區：</span><span class="sxs-lookup"><span data-stu-id="36533-p101">Because this cmdlet returns all the conference directories in your organization, you may want to limit the results to only the pool you want to decommission. For example, if you want to decommission a pool with the fully qualified domain name (FQDN) pool01.contoso.net:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="36533-110">此 Cmdlet 會傳回服務 ID 中包含 FQDN pool01.contoso.net 的所有會議目錄。</span><span class="sxs-lookup"><span data-stu-id="36533-110">This cmdlet returns all the conference directories where service ID contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="36533-111">若要移動會議目錄，請針對集區中的每個會議目錄執行下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="36533-111">To move conference directories, run the following for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="36533-112">例如：</span><span class="sxs-lookup"><span data-stu-id="36533-112">For example:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> <span data-ttu-id="36533-113">您可能會遇到下列錯誤：由於 Lync Server 管理命令介面需要從 Active Directory 更新一組許可權所導致。</span><span class="sxs-lookup"><span data-stu-id="36533-113">You may experience an error, shown below, that is caused by the Lync Server Management Shell requiring an updated set of permissions from Active Directory.</span></span> <span data-ttu-id="36533-114">若要解決此錯誤，請關閉目前的視窗，並開啟新的 Lync Server 管理命令介面，然後再次執行命令。</span><span class="sxs-lookup"><span data-stu-id="36533-114">To resolve the error, closed the current window and open a new Lync Server Management Shell and run the command again.</span></span>



</div>

<span data-ttu-id="36533-115">![Move-CsConferenceDirectory 錯誤輸出](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory 錯誤輸出")</span><span class="sxs-lookup"><span data-stu-id="36533-115">![Move-CsConferenceDirectory error output](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory error output")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

