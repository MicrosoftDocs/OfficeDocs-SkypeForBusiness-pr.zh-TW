---
title: Lync Server 2013：設定用戶端電腦上的個人連絡人存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the personal contacts store on client computers
ms:assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721922(v=OCS.15)
ms:contentKeyID: 49733857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4f9b7bbb50b5e63e87904d29a01715fcdcac8c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a>針對 Lync Server 2013 設定用戶端電腦上的個人連絡人存放區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-05_

如果您整合的是 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013，建議您在執行 Microsoft Lync 2010 的任何用戶端電腦上設定個人連絡人存放區。 特別是，您應該將 Lync 設定為使用 Exchange 做為個人連絡人存放區，同時請確定使用者無法覆寫該決定。 您可以在每個用戶端電腦上建立並設定登錄值來完成這項工作。

請注意，執行 Lync 2013 的電腦不需要這麼做。

若要在單一電腦上設定此值，請完成下列程式：

1.  在用戶端電腦上，按一下 [**開始**]，然後按一下 [**執行**]。

2.  在 [**執行**] 對話方塊中，輸入 regedit，然後按 enter。

3.  在 [登錄編輯程式] 中，展開 [ **HKEY\_本機\_電腦**]、[**軟體**]、[**原則**]、[ **Microsoft**]，然後展開 [ **Communicator**]。

4.  以滑鼠右鍵按一下 [ **Communicator**]，指向 [**新增**]，然後按一下 **[DWORD （32位）] 值**。

5.  建立新值之後，請輸入**PersonalContactStoreOverride** ，然後按 enter 鍵來重新命名值。

6.  確認 PersonalContactStoreOverride 的值設定為0，然後關閉 [登錄編輯程式]。

如果您需要在多部電腦上進行相同的變更，您可以建立自訂的群組原則物件來執行此動作。 如需詳細資訊，請參閱位於[http://go.microsoft.com/fwlink/p/?LinkId=268543](http://go.microsoft.com/fwlink/p/?linkid=268543)的群群組原則檔。

</div>

<span> </span>

</div>

</div>

</div>

