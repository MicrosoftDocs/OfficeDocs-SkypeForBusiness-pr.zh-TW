---
title: Lync Server 2013： 用戶端電腦上設定的個人連絡人存放區
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
ms.openlocfilehash: e035c360d339b48157969c75a1702beff03da634
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154225"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a>Lync Server 2013 的用戶端電腦上設定的個人連絡人存放區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-02-05_

如果您要整合 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 它被建議您在執行 Microsoft Lync 2010 的任何用戶端電腦上設定的個人連絡人存放區。 特別是，您應該設定為個人連絡人存放區，使用 Exchange，並在此同時，請確定使用者不能夠決定會覆寫 Lync。 這可以是經由建立及設定每個用戶端電腦上的登錄值。

請注意這不需要在執行 Lync 2013 的電腦上。

若要設定此值在單一電腦上，完成下列程序：

1.  用戶端電腦上，按一下 [**開始]** ，然後按一下 [**執行**。

2.  在 [執行]**** 對話方塊中，輸入 regedit，然後按 ENTER。

3.  在 「 登錄編輯程式中，依序展開 [ **HKEY\_本機\_機器**、 展開**軟體**、 展開 [**原則**]，依序展開 [ **Microsoft**，，然後展開**Communicator**。

4.  以滑鼠右鍵按一下**Communicator**，並指向 [**新增**]，然後按一下 [ **DWORD （32 位元） 值**。

5.  建立新的值之後，輸入**PersonalContactStoreOverride** ，然後按 ENTER 以數值重新命名。

6.  確認 value of PersonalContactStoreOverride 值已設為 0，然後關閉 [登錄編輯程式。

如果您需要在多部電腦上進行相同變更您可以藉由建立自訂的群組原則物件來執行此動作。 如需詳細資訊，請參閱群組原則文件[https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?linkid=268543)。

</div>

<span> </span>

</div>

</div>

</div>

