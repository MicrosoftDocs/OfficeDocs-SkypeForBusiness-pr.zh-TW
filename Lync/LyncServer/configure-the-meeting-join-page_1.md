---
title: 設定會議加入頁面
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 9b0829037377c15f8690c36f29f8775f9e5a56c6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="5d21f-102">設定會議加入頁面</span><span class="sxs-lookup"><span data-stu-id="5d21f-102">Configure the meeting join page</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d21f-103">_**主題上次修改日期：** 2012年-12-14_</span><span class="sxs-lookup"><span data-stu-id="5d21f-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="5d21f-104">當使用者按一下會議中的連結會議邀請，會議加入頁面會偵測到使用者的電腦上是否已安裝 Lync 2013 用戶端。</span><span class="sxs-lookup"><span data-stu-id="5d21f-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="5d21f-105">若已安裝用戶端，將會開啟該用戶端，然後加入會議。</span><span class="sxs-lookup"><span data-stu-id="5d21f-105">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="5d21f-106">如果未安裝在用戶端，預設的 2013年版的 Microsoft Lync Web App 會開啟。</span><span class="sxs-lookup"><span data-stu-id="5d21f-106">If a client is not installed, by default the 2013 version of Microsoft Lync Web App opens.</span></span>

<span data-ttu-id="5d21f-107">您可以修改行為的會議加入頁面如果您想要允許使用者加入會議與 Office Communicator 2007 R2 或 Lync 2010 Attendant。</span><span class="sxs-lookup"><span data-stu-id="5d21f-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="5d21f-108">已從 Lync Server 2013 控制台]，移除這些組態選項，但您使用 CsWebServiceConfiguration 指令程式來設定。</span><span class="sxs-lookup"><span data-stu-id="5d21f-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a><span data-ttu-id="5d21f-109">會議加入頁面的 CsWebServiceConfiguration 參數</span><span class="sxs-lookup"><span data-stu-id="5d21f-109">Meeting Join Page CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d21f-110">CsWebServiceConfiguration 參數</span><span class="sxs-lookup"><span data-stu-id="5d21f-110">CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="5d21f-111">描述</span><span class="sxs-lookup"><span data-stu-id="5d21f-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d21f-112">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="5d21f-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="5d21f-113">如果設為 True，使用以外的 Lync 用戶端應用程式加入會議的使用者將能夠使用 Office Communicator 2007 R2 來加入會議的機會。</span><span class="sxs-lookup"><span data-stu-id="5d21f-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="5d21f-114">預設值為 False。</span><span class="sxs-lookup"><span data-stu-id="5d21f-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d21f-115">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="5d21f-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="5d21f-p104">此參數設為 True 時，就會自動擴充參加線上會議的其他選項 (例如 Office Communicator 2007 R2)，並且對使用者顯示。設為 False (預設值) 時，可使用這些選項，但使用者必須自行顯示選項清單。</span><span class="sxs-lookup"><span data-stu-id="5d21f-p104">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users. When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="5d21f-118">若要設定會議加入頁面使用 Lync Server 2013 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="5d21f-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="5d21f-119">啟動 Lync Server 2013 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="5d21f-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="5d21f-120">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="5d21f-120">Run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration
    
    <span data-ttu-id="5d21f-121">此 Cmdlet 會傳回 Web 服務設定。</span><span class="sxs-lookup"><span data-stu-id="5d21f-121">This cmdlet returns the web service configuration settings.</span></span>

3.  <span data-ttu-id="5d21f-122">執行下列命令，參數設為 True 或 False，取決於偏好 （如需此 cmdlet 之參數的詳細資訊，請參閱 Lync Server 2013 管理命令介面文件）：</span><span class="sxs-lookup"><span data-stu-id="5d21f-122">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

