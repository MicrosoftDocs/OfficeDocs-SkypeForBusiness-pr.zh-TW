---
title: 設定會議加入頁面
description: 設定會議加入頁面。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the meeting join page
ms:assetid: 036c9d03-ad95-4d63-a3d8-6cae1a8ad530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204635(v=OCS.15)
ms:contentKeyID: 48183260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af49a57a6844c59bf6f6631d996d8efe12152c52
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542959"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="6e6d5-103">設定會議加入頁面</span><span class="sxs-lookup"><span data-stu-id="6e6d5-103">Configure the meeting join page</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e6d5-104">_**主題上次修改日期：** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="6e6d5-104">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="6e6d5-105">當使用者按一下會議邀請中的會議連結時，[會議加入] 頁面便會偵測使用者電腦上是否已安裝 Lync 2013 用戶端。</span><span class="sxs-lookup"><span data-stu-id="6e6d5-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="6e6d5-106">若已安裝用戶端，將會開啟該用戶端，然後加入會議。</span><span class="sxs-lookup"><span data-stu-id="6e6d5-106">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="6e6d5-107">若未安裝用戶端，則預設會開啟2013版本的 Lync Web App。</span><span class="sxs-lookup"><span data-stu-id="6e6d5-107">If a client is not installed, by default the 2013 version of Lync Web App opens.</span></span>

<span data-ttu-id="6e6d5-108">如果您想要允許使用者加入使用 Office Communicator 2007 R2 或 Lync 2010 的會議，您可以修改會議加入頁面的行為。</span><span class="sxs-lookup"><span data-stu-id="6e6d5-108">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="6e6d5-109">這些設定選項已從 Lync Server 2013 控制台中移除，但您使用 CsWebServiceConfiguration Cmdlet 進行設定。</span><span class="sxs-lookup"><span data-stu-id="6e6d5-109">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a><span data-ttu-id="6e6d5-110">會議加入頁面的 CsWebServiceConfiguration 參數</span><span class="sxs-lookup"><span data-stu-id="6e6d5-110">Meeting Join Page CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6e6d5-111">CsWebServiceConfiguration 參數</span><span class="sxs-lookup"><span data-stu-id="6e6d5-111">CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="6e6d5-112">描述</span><span class="sxs-lookup"><span data-stu-id="6e6d5-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e6d5-113">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="6e6d5-113">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="6e6d5-114">若設為 True，使用 Lync 以外的用戶端應用程式加入會議的使用者，將有機會利用 Office Communicator 2007 R2 加入會議。</span><span class="sxs-lookup"><span data-stu-id="6e6d5-114">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="6e6d5-115">預設值為 False。</span><span class="sxs-lookup"><span data-stu-id="6e6d5-115">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e6d5-116">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="6e6d5-116">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="6e6d5-p104">此參數設為 True 時，就會自動擴充參加線上會議的其他選項 (例如 Office Communicator 2007 R2)，並且對使用者顯示。設為 False (預設值) 時，可使用這些選項，但使用者必須自行顯示選項清單。</span><span class="sxs-lookup"><span data-stu-id="6e6d5-p104">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users. When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="6e6d5-119">使用 Lync Server 2013 管理命令介面設定會議加入頁面</span><span class="sxs-lookup"><span data-stu-id="6e6d5-119">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="6e6d5-120">啟動 Lync Server 2013 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="6e6d5-120">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="6e6d5-121">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="6e6d5-121">Run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration
    
    <span data-ttu-id="6e6d5-122">此 Cmdlet 會傳回 Web 服務設定。</span><span class="sxs-lookup"><span data-stu-id="6e6d5-122">This cmdlet returns the web service configuration settings.</span></span>

3.  <span data-ttu-id="6e6d5-123">執行下列命令，並將參數設定為 True 或 False，這取決於您的喜好設定 (如需此 Cmdlet 之參數的詳細資訊，請參閱 Lync Server 2013 管理命令介面檔) ：</span><span class="sxs-lookup"><span data-stu-id="6e6d5-123">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

