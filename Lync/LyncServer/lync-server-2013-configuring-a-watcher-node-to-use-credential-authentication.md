---
title: Lync Server 2013： 設定監看員節點以使用認證驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use credential authentication
ms:assetid: 032e33f3-9483-42e6-a33c-347eb6779597
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204632(v=OCS.15)
ms:contentKeyID: 48183255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d38a06c7ea40bd30f962484c8ce0d882c9633bf0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035135"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a>設定監看員節點以使用 Lync Server 2013 中的認證驗證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-20 個_

如果您的監看員節點電腦位於周邊網路外部，則必須遵循稍微不同的程序，以設定監看員節點執行綜合交易。具體而言，您不應該建立信任的應用程式集區和信任的應用程式，且您必須安裝憑證，讓監看員節點能夠將通知傳送至周邊網路內的電腦。這表示您必須完成下列兩項工作：

  - 更新電腦之 RTC Local Read-only Administrators 群組中的成員資格

  - 安裝監看員節點設定檔案

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a>更新 RTC Local Read-Only Administrators 群組中的成員資格

如果您的監看員節點電腦位於周邊網路外部，則必須將網路服務帳戶新增至監看員節點電腦上的 RTC Local Read-only Administrators 群組。若要執行這項操作，請在監看員節點上完成下列程序：

1.  按一下 [開始]****，然後以滑鼠右鍵按一下 [電腦]****，再按一下 [管理]****。

2.  在伺服器管理員中，依序展開 [設定]**** 及 [本機使用者和群組]****，然後按一下 [群組]****。

3.  在 [群組] 窗格中，按兩下 [RTC Local Read-only Administrators]****。

4.  在 [RTC Local Read-only Administrators 內容]**** 對話方塊中，按一下 [新增]****。

5.  在 [選取使用者、電腦、服務帳戶或群組]**** 對話方塊中，按一下 [位置]****。

6.  在 [位置]**** 對話方塊中，選取監看員節點電腦的名稱，然後按一下 [確定]****。

7.  在 [輸入物件名稱來選取]**** 方塊中，輸入 [網路服務]****，然後按一下 [確定]****。

8.  在 [RTC Local Read-only Administrators 內容]**** 對話方塊中，按一下 [確定]****，然後關閉 [伺服器管理員]****。

重新啟動監看員節點電腦。

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a>安裝監看員節點設定檔案

重新啟動監看員節點電腦之後，下一個步驟是執行 Watchernode.msi 檔案。 若要執行此檔案，請按一下 [**開始**，按一下 [**所有程式]**、 按一下 [ **Lync Server 2013**中，，然後按一下 [ **Lync Server 管理命令介面**就可以開啟 Lync Server 2013 管理命令介面。 在 [Lync Server 管理命令介面中，輸入下列命令並按 ENTER （務必和指定 Watchernode.msi 副本的實際路徑）：

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> 如前所述，Watchernode.msi 也可以透過命令視窗來執行。若要開啟命令視窗，請按一下 [開始]<STRONG></STRONG>，然後以滑鼠右鍵按一下 [命令提示字元]<STRONG></STRONG>，再按一下 [以系統管理員身分執行]<STRONG></STRONG>。開啟命令視窗時，輸入與稍早所示相同的命令。



</div>

您可以在無法將監看員節點設為信任的應用程式集區時，使用交涉模式。 在此模式中，系統管理員必須在監看員節點上管理測試使用者密碼。

</div>

</div>

<span> </span>

</div>

</div>

</div>

