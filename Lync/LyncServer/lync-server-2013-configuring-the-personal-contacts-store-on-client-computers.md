---
title: Lync Server 2013：在用戶端電腦上設定個人連絡人存放區
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
ms.openlocfilehash: 6020182c0083ecadcb65c07fa71be213f9458f0f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532340"
---
# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a>在用戶端電腦上為 Lync Server 2013 設定個人連絡人存放區

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-05_

如果您要整合 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013，建議您在任何執行 Microsoft Lync 2010 的用戶端電腦上設定個人連絡人存放區。 尤其是，您應該將 Lync 設定為使用 Exchange 做為個人連絡人存放區，並同時確保使用者不能覆寫該決策。 您可以在每一部用戶端電腦上建立及設定登錄值，以完成此動作。

請注意，在執行 Lync 2013 的電腦上，這不是必要的。

若要在單一電腦上設定此值，請完成下列程式：

1.  在用戶端電腦上，按一下 [ **開始** ]，然後按一下 [ **執行**]。

2.  在 [執行]**** 對話方塊中，輸入 regedit，然後按 ENTER。

3.  在登錄編輯程式中，展開 [ **HKEY \_ 本機 \_ 電腦**]，展開 [ **軟體**]，展開 [ **原則**]，展開 [ **Microsoft**]，然後展開 [ **Communicator**]。

4.  以滑鼠右鍵按一下 [ **Communicator**]，指向 [ **新增**]，然後按一下 [ **DWORD (32-bit) 值**]。

5.  建立新值後，輸入 **PersonalContactStoreOverride** ，然後按 enter 鍵來重新命名值。

6.  確認 PersonalContactStoreOverride 的值設為0，然後關閉 [登錄編輯程式]。

如果您需要在多部電腦上進行相同的變更，您可以建立自訂的群組原則物件。 如需詳細資訊，請參閱的群組原則檔 [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?linkid=268543) 。

</div>

<span> </span>

</div>

</div>

</div>

