---
title: Lync Server 2013：設定會議加入頁面
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting join page
ms:assetid: 45880423-47f4-49af-b825-cbd8e3fc1046
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204861(v=OCS.15)
ms:contentKeyID: 48184037
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c191bbc8927790345e7f969c38e4bf1a74ec3bdb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532320"
---
# <a name="configuring-the-meeting-join-page-in-lync-server-2013"></a><span data-ttu-id="86290-102">在 Lync Server 2013 中設定會議加入頁面</span><span class="sxs-lookup"><span data-stu-id="86290-102">Configuring the meeting join page in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86290-103">_**主題上次修改日期：** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="86290-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="86290-104">當使用者按一下會議邀請中的會議連結時，[會議加入] 頁面便會偵測使用者電腦上是否已安裝 Lync 2013 用戶端。</span><span class="sxs-lookup"><span data-stu-id="86290-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="86290-105">如果已安裝用戶端，則用戶端會開啟並加入會議。</span><span class="sxs-lookup"><span data-stu-id="86290-105">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="86290-106">若未安裝用戶端，則預設會開啟2013版本的 Lync Web App。</span><span class="sxs-lookup"><span data-stu-id="86290-106">If a client is not installed, by default the 2013 version of Lync Web App opens.</span></span>

<span data-ttu-id="86290-107">如果您想要允許使用者加入使用 Office Communicator 2007 R2 或 Lync 2010 的會議，您可以修改會議加入頁面的行為。</span><span class="sxs-lookup"><span data-stu-id="86290-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="86290-108">這些設定選項已從 Lync Server 2013 控制台中移除，但您使用 Set-CsWebServiceConfiguration Cmdlet 進行設定。</span><span class="sxs-lookup"><span data-stu-id="86290-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-set-cswebserviceconfiguration-parameters"></a><span data-ttu-id="86290-109">會議加入頁面 Set-CsWebServiceConfiguration 參數</span><span class="sxs-lookup"><span data-stu-id="86290-109">Meeting Join Page Set-CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86290-110">Set-CsWebServiceConfiguration 參數</span><span class="sxs-lookup"><span data-stu-id="86290-110">Set-CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="86290-111">描述</span><span class="sxs-lookup"><span data-stu-id="86290-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86290-112">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="86290-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="86290-113">若設為 True，使用 Lync 以外的用戶端應用程式加入會議的使用者，將有機會利用 Office Communicator 2007 R2 加入會議。</span><span class="sxs-lookup"><span data-stu-id="86290-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="86290-114">預設值為 False。</span><span class="sxs-lookup"><span data-stu-id="86290-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86290-115">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="86290-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="86290-p104">此參數設為 True 時，就會自動擴充參加線上會議的其他選項 (例如 Office Communicator 2007 R2)，並且對使用者顯示。設為 False (預設值) 時，可使用這些選項，但使用者必須自行顯示選項清單。</span><span class="sxs-lookup"><span data-stu-id="86290-p104">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users. When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="86290-118">使用 Lync Server 2013 管理命令介面設定會議加入頁面</span><span class="sxs-lookup"><span data-stu-id="86290-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="86290-119">啟動 Lync Server 2013 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="86290-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="86290-120">如果要檢視 Web 服務組態設定，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="86290-120">To view the web service configuration settings, run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration

3.  <span data-ttu-id="86290-121">執行下列命令，並將參數設定為 True 或 False，這取決於您的喜好設定 (如需此 Cmdlet 之參數的詳細資訊，請參閱 Lync Server 2013 管理命令介面檔) 中的 [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) 。</span><span class="sxs-lookup"><span data-stu-id="86290-121">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) in the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="86290-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="86290-122">See Also</span></span>


[<span data-ttu-id="86290-123">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="86290-123">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

