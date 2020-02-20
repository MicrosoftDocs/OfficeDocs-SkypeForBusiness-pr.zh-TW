---
title: Lync Server 2013： 設定會議加入頁面
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
ms.openlocfilehash: 977903d8d85b3eaa4d944e8b3e62ec0df629c1d0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154235"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-join-page-in-lync-server-2013"></a><span data-ttu-id="41993-102">Lync Server 2013 中設定會議加入頁面</span><span class="sxs-lookup"><span data-stu-id="41993-102">Configuring the meeting join page in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41993-103">_**主題上次修改日期：** 2012年-12-14_</span><span class="sxs-lookup"><span data-stu-id="41993-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="41993-104">當使用者按一下會議中的連結會議邀請，會議加入頁面會偵測到使用者的電腦上是否已安裝 Lync 2013 用戶端。</span><span class="sxs-lookup"><span data-stu-id="41993-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="41993-105">如果已安裝用戶端，則用戶端會開啟並加入會議。</span><span class="sxs-lookup"><span data-stu-id="41993-105">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="41993-106">如果未安裝在用戶端，預設的 Lync Web App 2013 版本會開啟。</span><span class="sxs-lookup"><span data-stu-id="41993-106">If a client is not installed, by default the 2013 version of Lync Web App opens.</span></span>

<span data-ttu-id="41993-107">您可以修改行為的會議加入頁面如果您想要允許使用者加入會議與 Office Communicator 2007 R2 或 Lync 2010 Attendant。</span><span class="sxs-lookup"><span data-stu-id="41993-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="41993-108">已從 Lync Server 2013 控制台]，移除這些組態選項，但您使用 Set-cswebserviceconfiguration cmdlet 來設定。</span><span class="sxs-lookup"><span data-stu-id="41993-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-set-cswebserviceconfiguration-parameters"></a><span data-ttu-id="41993-109">會議加入頁面 Set-CsWebServiceConfiguration 參數</span><span class="sxs-lookup"><span data-stu-id="41993-109">Meeting Join Page Set-CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41993-110">Set-CsWebServiceConfiguration 參數</span><span class="sxs-lookup"><span data-stu-id="41993-110">Set-CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="41993-111">描述</span><span class="sxs-lookup"><span data-stu-id="41993-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41993-112">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="41993-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="41993-113">如果設為 True，使用以外的 Lync 用戶端應用程式加入會議的使用者將能夠使用 Office Communicator 2007 R2 來加入會議的機會。</span><span class="sxs-lookup"><span data-stu-id="41993-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="41993-114">預設值為 False。</span><span class="sxs-lookup"><span data-stu-id="41993-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41993-115">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="41993-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="41993-p104">此參數設為 True 時，就會自動擴充參加線上會議的其他選項 (例如 Office Communicator 2007 R2)，並且對使用者顯示。設為 False (預設值) 時，可使用這些選項，但使用者必須自行顯示選項清單。</span><span class="sxs-lookup"><span data-stu-id="41993-p104">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users. When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="41993-118">若要設定會議加入頁面使用 Lync Server 2013 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="41993-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="41993-119">啟動 Lync Server 2013 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="41993-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="41993-120">如果要檢視 Web 服務組態設定，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="41993-120">To view the web service configuration settings, run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration

3.  <span data-ttu-id="41993-121">執行下列命令，參數設為 True 或 False，取決於偏好 （如需此 cmdlet 之參數的詳細資訊，請參閱[Set-cswebserviceconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) Lync Server 2013 管理命令介面文件中）：</span><span class="sxs-lookup"><span data-stu-id="41993-121">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) in the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="41993-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="41993-122">See Also</span></span>


[<span data-ttu-id="41993-123">Set-cswebserviceconfiguration</span><span class="sxs-lookup"><span data-stu-id="41993-123">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

