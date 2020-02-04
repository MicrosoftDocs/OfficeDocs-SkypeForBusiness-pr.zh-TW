---
title: 移動會議目錄
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ae7633d638571410c93cfefe87d9e333731a4bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a><span data-ttu-id="ae6a6-102">移動會議目錄</span><span class="sxs-lookup"><span data-stu-id="ae6a6-102">Move conference directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae6a6-103">_**主題上次修改日期：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="ae6a6-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="ae6a6-104">在解除池的授權前，您必須針對 Office 通訊伺服器 2007 R2 池中的每個會議目錄執行下列程式。</span><span class="sxs-lookup"><span data-stu-id="ae6a6-104">Before decommissioning a pool, you need to perform the following procedure for each conference directory in your Office Communications Server 2007 R2 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="ae6a6-105">將會議目錄移至 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae6a6-105">To move a conference directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="ae6a6-106">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="ae6a6-106">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="ae6a6-107">若要取得貴組織中會議目錄的身分識別，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ae6a6-107">To obtain the identity of the conference directories in your organization, run the following commands:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="ae6a6-108">由於這個 Cmdlet 會傳回貴組織中的所有會議目錄，因此您可能會想要將結果限制在您要解除授權的池中。</span><span class="sxs-lookup"><span data-stu-id="ae6a6-108">Because this cmdlet returns all the conference directories in your organization, you may want to limit the results to only the pool you want to decommission.</span></span> <span data-ttu-id="ae6a6-109">例如，如果您想要使用完整功能變數名稱（FQDN）來解除池中的 pool01.contoso.net：</span><span class="sxs-lookup"><span data-stu-id="ae6a6-109">For example, if you want to decommission a pool with the fully qualified domain name (FQDN) pool01.contoso.net:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="ae6a6-110">這個 Cmdlet 會傳回服務識別碼包含 FQDN pool01.contoso.net 的所有會議目錄。</span><span class="sxs-lookup"><span data-stu-id="ae6a6-110">This cmdlet returns all the conference directories where service ID contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="ae6a6-111">若要移動會議目錄，請針對池中的每個會議目錄執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ae6a6-111">To move conference directories, run the following for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="ae6a6-112">例如：</span><span class="sxs-lookup"><span data-stu-id="ae6a6-112">For example:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> <span data-ttu-id="ae6a6-113">您可能會遇到下列錯誤（如下所示），這是因為 Lync Server 管理命令介面需要來自 Active Directory 的更新組許可權。</span><span class="sxs-lookup"><span data-stu-id="ae6a6-113">You may experience an error, shown below, that is caused by the Lync Server Management Shell requiring an updated set of permissions from Active Directory.</span></span> <span data-ttu-id="ae6a6-114">若要解決錯誤，請關閉目前的視窗，然後開啟新的 Lync Server 管理命令介面，然後再次執行命令。</span><span class="sxs-lookup"><span data-stu-id="ae6a6-114">To resolve the error, closed the current window and open a new Lync Server Management Shell and run the command again.</span></span>



</div>

<span data-ttu-id="ae6a6-115">![Move-CsConferenceDirectory 錯誤輸出](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory 錯誤輸出")</span><span class="sxs-lookup"><span data-stu-id="ae6a6-115">![Move-CsConferenceDirectory error output](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory error output")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

