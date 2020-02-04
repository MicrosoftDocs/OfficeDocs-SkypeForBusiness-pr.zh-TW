---
title: Lync Server 2013：驗證結構描述複寫
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
ms.openlocfilehash: e7ea90012c116bb66caf16313d930c6f05db4413
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a><span data-ttu-id="a1628-102">在 Lync Server 2013 中驗證 Active Directory 結構描述複寫</span><span class="sxs-lookup"><span data-stu-id="a1628-102">Verifying Active Directory schema replication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1628-103">_**主題上次修改日期：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="a1628-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="a1628-104">在執行林準備之前，請手動確認架構分區已複製。</span><span class="sxs-lookup"><span data-stu-id="a1628-104">Before you run forest preparation, manually verify that the schema partition has been replicated.</span></span>

<div>

## <a name="to-manually-verify-schema-replication"></a><span data-ttu-id="a1628-105">手動驗證架構複製</span><span class="sxs-lookup"><span data-stu-id="a1628-105">To manually verify schema replication</span></span>

1.  <span data-ttu-id="a1628-106">以企業系統管理員群組的成員身分登入網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="a1628-106">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="a1628-107">按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **adsi 編輯**]，以開啟 [adsi 編輯]。</span><span class="sxs-lookup"><span data-stu-id="a1628-107">Open ADSI Edit by clicking **Start**, clicking **Administrative Tools**, and then clicking **ADSI Edit**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="a1628-108">或者，您可以從命令列執行<STRONG>adsiedit services.msc。</STRONG></span><span class="sxs-lookup"><span data-stu-id="a1628-108">Alternatively, you can run <STRONG>adsiedit.msc</STRONG> from the command line.</span></span>

    
    </div>

3.  <span data-ttu-id="a1628-109">在 Microsoft 管理主控台（MMC）樹狀結構中，如果尚未選取，請按一下 [ **ADSI 編輯**]。</span><span class="sxs-lookup"><span data-stu-id="a1628-109">In the Microsoft Management Console (MMC) tree, if it is not already selected, click **ADSI Edit**.</span></span>

4.  <span data-ttu-id="a1628-110">在 [**動作**] 功能表上，按一下 **[連線至]**。</span><span class="sxs-lookup"><span data-stu-id="a1628-110">On the **Action** menu, click **Connect to**.</span></span>

5.  <span data-ttu-id="a1628-111">在 [連線**設定**] 對話方塊中的 [**選取已知命名內容**] 底下，選取 [**架構**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a1628-111">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>

6.  <span data-ttu-id="a1628-112">在架構容器底下，搜尋 CN = ms-SIP-SchemaVersion。</span><span class="sxs-lookup"><span data-stu-id="a1628-112">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="a1628-113">如果此物件存在，且**rangeUpper**屬性的值為1150，且**rangeLower**屬性的值為3，則架構已成功更新並複製。</span><span class="sxs-lookup"><span data-stu-id="a1628-113">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="a1628-114">如果此物件不存在，或**rangeUpper**和**rangeLower**屬性的值不是指定的，則架構並未被修改或未複製。</span><span class="sxs-lookup"><span data-stu-id="a1628-114">If this object does not exist or the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a1628-115">請參閱</span><span class="sxs-lookup"><span data-stu-id="a1628-115">See Also</span></span>


[<span data-ttu-id="a1628-116">在 Lync Server 2013 中執行 Active Directory 架構準備</span><span class="sxs-lookup"><span data-stu-id="a1628-116">Running Active Directory schema preparation in Lync Server 2013</span></span>](lync-server-2013-running-schema-preparation.md)  


[<span data-ttu-id="a1628-117">在 Lync Server 2013 中準備 Active Directory 結構描述</span><span class="sxs-lookup"><span data-stu-id="a1628-117">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

