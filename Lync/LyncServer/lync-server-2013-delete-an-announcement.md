---
title: Lync Server 2013：刪除公告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an announcement
ms:assetid: 26ea7149-4470-4c22-9bab-8a4065aca44e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687998(v=OCS.15)
ms:contentKeyID: 49733588
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91a15057e4785a16e7fc632422573ee02d1d920b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-announcement-in-lync-server-2013"></a><span data-ttu-id="11a58-102">在 Lync Server 2013 中刪除公告</span><span class="sxs-lookup"><span data-stu-id="11a58-102">Delete an announcement in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11a58-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="11a58-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="11a58-104">使用下列程式來刪除用於呼叫未指派號碼的宣告。</span><span class="sxs-lookup"><span data-stu-id="11a58-104">Use the following procedure to delete an announcement that is used for calls to unassigned numbers.</span></span>

<div>

## <a name="to-delete-an-announcement"></a><span data-ttu-id="11a58-105">刪除公告</span><span class="sxs-lookup"><span data-stu-id="11a58-105">To delete an announcement</span></span>

1.  <span data-ttu-id="11a58-106">登入 Lync Server 管理命令介面安裝為 RTCUniversalServerAdmins 群組的成員的電腦，或使用[Lync server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述的必要使用者許可權。</span><span class="sxs-lookup"><span data-stu-id="11a58-106">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="11a58-107">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="11a58-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="11a58-108">列出貴組織中的所有宣告。</span><span class="sxs-lookup"><span data-stu-id="11a58-108">List all the announcements in your organization.</span></span> <span data-ttu-id="11a58-109">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="11a58-109">At the command line, run:</span></span>
    
        Get-CsAnnouncement

4.  <span data-ttu-id="11a58-110">在產生的清單中，找出您要刪除的宣告，然後複製 GUID。</span><span class="sxs-lookup"><span data-stu-id="11a58-110">In the resulting list, locate the announcement you want to delete, and copy the GUID.</span></span> <span data-ttu-id="11a58-111">然後，在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="11a58-111">Then, at the command line, run:</span></span>
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>" 
    
    <span data-ttu-id="11a58-112">例如：</span><span class="sxs-lookup"><span data-stu-id="11a58-112">For example:</span></span>
    
        Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="11a58-113">如需更多選項的詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement">CsAnnouncement</A>及<A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement">Remove-CsAnnouncement</A>。</span><span class="sxs-lookup"><span data-stu-id="11a58-113">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement">Get-CsAnnouncement</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement">Remove-CsAnnouncement</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="11a58-114">請參閱</span><span class="sxs-lookup"><span data-stu-id="11a58-114">See Also</span></span>


[<span data-ttu-id="11a58-115">在 Lync Server 2013 中建立公告</span><span class="sxs-lookup"><span data-stu-id="11a58-115">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)  


[<span data-ttu-id="11a58-116">移除-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="11a58-116">Remove-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement)  
[<span data-ttu-id="11a58-117">CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="11a58-117">Get-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

