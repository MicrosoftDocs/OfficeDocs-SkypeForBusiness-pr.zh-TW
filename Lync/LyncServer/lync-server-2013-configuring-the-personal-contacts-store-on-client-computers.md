---
title: Lync Server 2013：設定用戶端電腦上的個人連絡人存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the personal contacts store on client computers
ms:assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721922(v=OCS.15)
ms:contentKeyID: 49733857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77e6e48593bb3dc7a11375b13346ad59b2f40c0e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a><span data-ttu-id="b426e-102">針對 Lync Server 2013 設定用戶端電腦上的個人連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="b426e-102">Configuring the personal contacts store on client computers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b426e-103">_**主題上次修改日期：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="b426e-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="b426e-104">如果您整合的是 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013，建議您在執行 Microsoft Lync 2010 的任何用戶端電腦上設定個人連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="b426e-104">If you are integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013 then it is recommended that you configure the personal contact store on any client computers running Microsoft Lync 2010.</span></span> <span data-ttu-id="b426e-105">特別是，您應該將 Lync 設定為使用 Exchange 做為個人連絡人存放區，同時請確定使用者無法覆寫該決定。</span><span class="sxs-lookup"><span data-stu-id="b426e-105">In particular, you should configure Lync to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="b426e-106">您可以在每個用戶端電腦上建立並設定登錄值來完成這項工作。</span><span class="sxs-lookup"><span data-stu-id="b426e-106">This can be done by creating and configuring a Registry value on each client computer.</span></span>

<span data-ttu-id="b426e-107">請注意，執行 Lync 2013 的電腦不需要這麼做。</span><span class="sxs-lookup"><span data-stu-id="b426e-107">Note that this is not required on computers running Lync 2013.</span></span>

<span data-ttu-id="b426e-108">若要在單一電腦上設定此值，請完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="b426e-108">To configure this value on a single computer, complete the following procedure:</span></span>

1.  <span data-ttu-id="b426e-109">在用戶端電腦上，按一下 [**開始**]，然後按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="b426e-109">On the client computer, click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="b426e-110">在 [**執行**] 對話方塊中，輸入 regedit，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="b426e-110">In the **Run** dialog box, type regedit and then press ENTER.</span></span>

3.  <span data-ttu-id="b426e-111">在 [登錄編輯程式] 中，展開 [ **HKEY\_本機\_電腦**]、[**軟體**]、[**原則**]、[ **Microsoft**]，然後展開 [ **Communicator**]。</span><span class="sxs-lookup"><span data-stu-id="b426e-111">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>

4.  <span data-ttu-id="b426e-112">以滑鼠右鍵按一下 [ **Communicator**]，指向 [**新增**]，然後按一下 **[DWORD （32位）] 值**。</span><span class="sxs-lookup"><span data-stu-id="b426e-112">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>

5.  <span data-ttu-id="b426e-113">建立新值之後，請輸入**PersonalContactStoreOverride** ，然後按 enter 鍵來重新命名值。</span><span class="sxs-lookup"><span data-stu-id="b426e-113">After the new value is created, type **PersonalContactStoreOverride** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="b426e-114">確認 PersonalContactStoreOverride 的值設定為0，然後關閉 [登錄編輯程式]。</span><span class="sxs-lookup"><span data-stu-id="b426e-114">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="b426e-115">如果您需要在多部電腦上進行相同的變更，您可以建立自訂的群組原則物件來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="b426e-115">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="b426e-116">如需詳細資訊，請參閱位於[http://go.microsoft.com/fwlink/p/?LinkId=268543](http://go.microsoft.com/fwlink/p/?linkid=268543)的群群組原則檔。</span><span class="sxs-lookup"><span data-stu-id="b426e-116">For details, see the Group Policy documentation at [http://go.microsoft.com/fwlink/p/?LinkId=268543](http://go.microsoft.com/fwlink/p/?linkid=268543).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

