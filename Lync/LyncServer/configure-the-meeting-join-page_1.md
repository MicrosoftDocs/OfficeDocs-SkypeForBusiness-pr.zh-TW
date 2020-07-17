---
title: 設定會議加入頁面
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the meeting join page
ms:assetid: a87319b7-3124-4262-8f9d-18138870ee2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205145(v=OCS.15)
ms:contentKeyID: 48185030
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a63354b9e0b0cf44ed44f53c91061578e01fecb5
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754501"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="a2556-102">設定會議加入頁面</span><span class="sxs-lookup"><span data-stu-id="a2556-102">Configure the meeting join page</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2556-103">_**主題上次修改日期：** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="a2556-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="a2556-104">當使用者按一下會議邀請中的會議連結時，[會議加入] 頁面便會偵測使用者電腦上是否已安裝 Lync 2013 用戶端。</span><span class="sxs-lookup"><span data-stu-id="a2556-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="a2556-105">若已安裝用戶端，將會開啟該用戶端，然後加入會議。</span><span class="sxs-lookup"><span data-stu-id="a2556-105">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="a2556-106">若未安裝用戶端，則預設會開啟2013版本的 Microsoft Lync Web App。</span><span class="sxs-lookup"><span data-stu-id="a2556-106">If a client is not installed, by default the 2013 version of Microsoft Lync Web App opens.</span></span>

<span data-ttu-id="a2556-107">如果您想要允許使用者加入使用 Office Communicator 2007 R2 或 Lync 2010 的會議，您可以修改會議加入頁面的行為。</span><span class="sxs-lookup"><span data-stu-id="a2556-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="a2556-108">這些設定選項已從 Lync Server 2013 控制台中移除，但您使用 CsWebServiceConfiguration Cmdlet 進行設定。</span><span class="sxs-lookup"><span data-stu-id="a2556-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a><span data-ttu-id="a2556-109">會議加入頁面的 CsWebServiceConfiguration 參數</span><span class="sxs-lookup"><span data-stu-id="a2556-109">Meeting Join Page CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a2556-110">CsWebServiceConfiguration 參數</span><span class="sxs-lookup"><span data-stu-id="a2556-110">CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="a2556-111">描述</span><span class="sxs-lookup"><span data-stu-id="a2556-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2556-112">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="a2556-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="a2556-113">若設為 True，使用 Lync 以外的用戶端應用程式加入會議的使用者，將有機會利用 Office Communicator 2007 R2 加入會議。</span><span class="sxs-lookup"><span data-stu-id="a2556-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="a2556-114">預設值為 False。</span><span class="sxs-lookup"><span data-stu-id="a2556-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2556-115">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="a2556-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="a2556-p104">此參數設為 True 時，就會自動擴充參加線上會議的其他選項 (例如 Office Communicator 2007 R2)，並且對使用者顯示。設為 False (預設值) 時，可使用這些選項，但使用者必須自行顯示選項清單。</span><span class="sxs-lookup"><span data-stu-id="a2556-p104">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users. When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="a2556-118">使用 Lync Server 2013 管理命令介面設定會議加入頁面</span><span class="sxs-lookup"><span data-stu-id="a2556-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="a2556-119">啟動 Lync Server 2013 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="a2556-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a2556-120">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="a2556-120">Run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration
    
    <span data-ttu-id="a2556-121">此 Cmdlet 會傳回 Web 服務設定。</span><span class="sxs-lookup"><span data-stu-id="a2556-121">This cmdlet returns the web service configuration settings.</span></span>

3.  <span data-ttu-id="a2556-122">執行下列命令，並將參數設定為 True 或 False，這取決於您的喜好設定（如需此 Cmdlet 之參數的詳細資訊，請參閱 Lync Server 2013 管理命令介面檔）：</span><span class="sxs-lookup"><span data-stu-id="a2556-122">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

