---
title: Lync Server 2013：設定會議加入頁面
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the meeting join page
ms:assetid: 45880423-47f4-49af-b825-cbd8e3fc1046
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204861(v=OCS.15)
ms:contentKeyID: 48184037
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 984386eb15aac3c3d2d46c9d7aaab53457915b39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974678"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-join-page-in-lync-server-2013"></a><span data-ttu-id="eb29c-102">在 Lync Server 2013 中設定會議加入頁面</span><span class="sxs-lookup"><span data-stu-id="eb29c-102">Configuring the meeting join page in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb29c-103">_**主題上次修改日期：** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="eb29c-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="eb29c-104">當使用者按一下會議邀請中的會議連結時，會議加入頁面會偵測到 Lync 2013 用戶端是否已安裝在使用者的電腦上。</span><span class="sxs-lookup"><span data-stu-id="eb29c-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="eb29c-105">如果已安裝用戶端，用戶端會開啟並加入會議。</span><span class="sxs-lookup"><span data-stu-id="eb29c-105">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="eb29c-106">如果未安裝用戶端，則預設會開啟2013版的 Lync Web App。</span><span class="sxs-lookup"><span data-stu-id="eb29c-106">If a client is not installed, by default the 2013 version of Lync Web App opens.</span></span>

<span data-ttu-id="eb29c-107">如果您想要允許使用者使用 Office Communicator 2007 R2 或 Lync 2010 應答加入會議，您可以修改會議加入頁面的行為。</span><span class="sxs-lookup"><span data-stu-id="eb29c-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="eb29c-108">這些設定選項已從 Lync Server 2013 [控制台] 中移除，但您可以使用 CsWebServiceConfiguration Cmdlet 進行設定。</span><span class="sxs-lookup"><span data-stu-id="eb29c-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-set-cswebserviceconfiguration-parameters"></a><span data-ttu-id="eb29c-109">會議加入頁面集-CsWebServiceConfiguration 參數</span><span class="sxs-lookup"><span data-stu-id="eb29c-109">Meeting Join Page Set-CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb29c-110">CsWebServiceConfiguration 參數</span><span class="sxs-lookup"><span data-stu-id="eb29c-110">Set-CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="eb29c-111">描述</span><span class="sxs-lookup"><span data-stu-id="eb29c-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb29c-112">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="eb29c-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="eb29c-113">如果設為 True，則使用 Lync 以外的用戶端應用程式加入會議的使用者將有機會使用 Office Communicator 2007 R2 加入會議。</span><span class="sxs-lookup"><span data-stu-id="eb29c-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="eb29c-114">預設值為 False。</span><span class="sxs-lookup"><span data-stu-id="eb29c-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb29c-115">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="eb29c-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="eb29c-116">當設定為 True 時，加入線上會議的替代選項（例如 Office Communicator 2007 R2）將會自動展開並向使用者顯示。</span><span class="sxs-lookup"><span data-stu-id="eb29c-116">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users.</span></span> <span data-ttu-id="eb29c-117">當設定為 False （預設值）時，這些選項將可供使用，但使用者將必須針對自己顯示選項清單。</span><span class="sxs-lookup"><span data-stu-id="eb29c-117">When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="eb29c-118">使用 Lync Server 2013 管理命令介面設定會議加入頁面</span><span class="sxs-lookup"><span data-stu-id="eb29c-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="eb29c-119">啟動 Lync Server 2013 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server Management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="eb29c-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="eb29c-120">若要查看 web 服務設定，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="eb29c-120">To view the web service configuration settings, run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration

3.  <span data-ttu-id="eb29c-121">根據您的喜好設定（如需此 Cmdlet 之參數的詳細資料，請參閱 Lync Server 2013 管理命令介面檔中的[設定 CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) ），執行下列命令，並將參數設定為 True 或 False。</span><span class="sxs-lookup"><span data-stu-id="eb29c-121">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) in the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eb29c-122">請參閱</span><span class="sxs-lookup"><span data-stu-id="eb29c-122">See Also</span></span>


[<span data-ttu-id="eb29c-123">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="eb29c-123">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

