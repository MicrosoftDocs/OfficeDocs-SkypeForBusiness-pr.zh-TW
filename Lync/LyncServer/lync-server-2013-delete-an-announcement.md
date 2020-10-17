---
title: Lync Server 2013：刪除宣告
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
ms.openlocfilehash: 95f425a461d628ccf7da6021c20b578f639fe605
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516190"
---
# <a name="delete-an-announcement-in-lync-server-2013"></a><span data-ttu-id="17b82-102">在 Lync Server 2013 中刪除宣告</span><span class="sxs-lookup"><span data-stu-id="17b82-102">Delete an announcement in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17b82-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="17b82-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="17b82-104">使用下列程序刪除未指派之號碼的電話所使用的宣告。</span><span class="sxs-lookup"><span data-stu-id="17b82-104">Use the following procedure to delete an announcement that is used for calls to unassigned numbers.</span></span>

<div>

## <a name="to-delete-an-announcement"></a><span data-ttu-id="17b82-105">刪除宣告</span><span class="sxs-lookup"><span data-stu-id="17b82-105">To delete an announcement</span></span>

1.  <span data-ttu-id="17b82-106">以 [Lync server 2013 的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述，登入安裝了 Lync Server 管理命令介面的電腦，以作為 RTCUniversalServerAdmins 群組的成員或必要的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="17b82-106">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="17b82-107">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="17b82-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="17b82-p101">列出組織中的所有宣告。在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="17b82-p101">List all the announcements in your organization. At the command line, run:</span></span>
    
        Get-CsAnnouncement

4.  <span data-ttu-id="17b82-p102">在結果清單中，找出您要刪除的宣告，並複製 GUID。然後在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="17b82-p102">In the resulting list, locate the announcement you want to delete, and copy the GUID. Then, at the command line, run:</span></span>
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>" 
    
    <span data-ttu-id="17b82-112">例如：</span><span class="sxs-lookup"><span data-stu-id="17b82-112">For example:</span></span>
    
        Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="17b82-113">如需更多選項的詳細資訊，請參閱 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement">CsAnnouncement</A> 和 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement">Remove-CsAnnouncement</A>。</span><span class="sxs-lookup"><span data-stu-id="17b82-113">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement">Get-CsAnnouncement</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement">Remove-CsAnnouncement</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="17b82-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="17b82-114">See Also</span></span>


[<span data-ttu-id="17b82-115">在 Lync Server 2013 中建立宣告</span><span class="sxs-lookup"><span data-stu-id="17b82-115">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)  


[<span data-ttu-id="17b82-116">Remove-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="17b82-116">Remove-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement)  
[<span data-ttu-id="17b82-117">CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="17b82-117">Get-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

