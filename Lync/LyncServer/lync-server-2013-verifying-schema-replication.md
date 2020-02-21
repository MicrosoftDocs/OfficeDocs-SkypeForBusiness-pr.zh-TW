---
title: 'Lync Server 2013: Cmdlet 執行架構準備'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verifying schema replication
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48185124
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f59704edacc9b7c9a04f4492ddad778b65401033
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a><span data-ttu-id="1411a-102">確認 Lync Server 2013 中的 Active Directory 架構準備</span><span class="sxs-lookup"><span data-stu-id="1411a-102">Verifying Active Directory schema replication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1411a-103">_**主題上次修改日期：** 2012年-10-29_</span><span class="sxs-lookup"><span data-stu-id="1411a-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="1411a-104">執行樹系準備之前，請手動驗證架構磁碟分割已複寫。</span><span class="sxs-lookup"><span data-stu-id="1411a-104">Before you run forest preparation, manually verify that the schema partition has been replicated.</span></span>

<div>

## <a name="to-manually-verify-schema-replication"></a><span data-ttu-id="1411a-105">若要手動驗證架構複寫</span><span class="sxs-lookup"><span data-stu-id="1411a-105">To manually verify schema replication</span></span>

1.  <span data-ttu-id="1411a-106">以 Enterprise Admins 群組成員身分登入網域控制站。</span><span class="sxs-lookup"><span data-stu-id="1411a-106">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="1411a-107">依序按一下 **[開始]**、**[系統管理工具]** 和 **[ADSI 編輯器]**，以開啟 [ADSI 編輯器]。</span><span class="sxs-lookup"><span data-stu-id="1411a-107">Open ADSI Edit by clicking **Start**, clicking **Administrative Tools**, and then clicking **ADSI Edit**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="1411a-108">或者，您可以從命令列執行<STRONG>adsiedit.msc</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="1411a-108">Alternatively, you can run <STRONG>adsiedit.msc</STRONG> from the command line.</span></span>

    
    </div>

3.  <span data-ttu-id="1411a-109">在 Microsoft Management Console (MMC) 樹狀目錄中，如果未選取，按一下 [ **Adsi 編輯器]**。</span><span class="sxs-lookup"><span data-stu-id="1411a-109">In the Microsoft Management Console (MMC) tree, if it is not already selected, click **ADSI Edit**.</span></span>

4.  <span data-ttu-id="1411a-110">在 **[執行]** 功能表上，按一下 **[連線到]**。</span><span class="sxs-lookup"><span data-stu-id="1411a-110">On the **Action** menu, click **Connect to**.</span></span>

5.  <span data-ttu-id="1411a-111">在 **[選取熟知的命名內容]** 的 **[連線設定]** 對話方塊中，選取 **[架構]**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1411a-111">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>

6.  <span data-ttu-id="1411a-112">在架構容器下，搜尋 CN=ms-RTC-SIP-SchemaVersion。</span><span class="sxs-lookup"><span data-stu-id="1411a-112">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="1411a-113">如果此物件存在，而 **rangeUpper** 屬性的值為 1150，**rangeLower** 屬性的值為 3，則表示已成功更新和複寫架構。</span><span class="sxs-lookup"><span data-stu-id="1411a-113">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="1411a-114">如果此物件不存在，或 **rangeUpper** 和 **rangeLower** 屬性不是上述指定的值，則表示未修改或未複寫架構。</span><span class="sxs-lookup"><span data-stu-id="1411a-114">If this object does not exist or the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1411a-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1411a-115">See Also</span></span>


[<span data-ttu-id="1411a-116">在 Lync Server 2013 中執行 Active Directory 架構準備</span><span class="sxs-lookup"><span data-stu-id="1411a-116">Running Active Directory schema preparation in Lync Server 2013</span></span>](lync-server-2013-running-schema-preparation.md)  


[<span data-ttu-id="1411a-117">準備 Lync Server 2013 中的 Active Directory 結構描述</span><span class="sxs-lookup"><span data-stu-id="1411a-117">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

