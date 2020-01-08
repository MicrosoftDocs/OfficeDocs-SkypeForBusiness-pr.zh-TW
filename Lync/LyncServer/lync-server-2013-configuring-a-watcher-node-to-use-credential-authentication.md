---
title: Lync Server 2013：將觀察程式節點設定為使用認證驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to use credential authentication
ms:assetid: 032e33f3-9483-42e6-a33c-347eb6779597
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204632(v=OCS.15)
ms:contentKeyID: 48183255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3746042e0fbf6c7342dd19085f563440b26bb0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a>在 Lync Server 2013 中將 [觀察程式] 節點設定為使用認證驗證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-20_

如果您的觀察程式節點電腦位於周邊網路之外，您必須遵循稍有不同的程式，才能設定該觀察程式節點執行綜合交易。 具體來說，您不應該建立信任的應用程式池和受信任的應用程式，而且您必須安裝可讓觀察程式節點傳送通知到周邊網路內電腦的憑證。 這表示您需要完成兩個不同的工作：

  - 更新電腦 RTC 本機唯讀系統管理員群組中的成員資格

  - 安裝觀察程式節點設定檔

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a>更新 RTC 本機唯讀系統管理員群組中的成員資格

如果您的觀察程式節點位於周邊網路之外，您必須將網路服務帳戶新增到 [程式] 節點電腦上的 RTC 本機唯讀系統管理員群組。 若要這樣做，請在 [觀察程式] 節點上完成下列程式：

1.  按一下 [**開始**]，以滑鼠右鍵按一下 [**電腦**]，然後按一下 [**管理**]。

2.  在 [伺服器管理員] 中，展開 [設定] **，展開 [****本機使用者和群組**]，然後按一下 [**群組**]。

3.  在 [群組] 窗格中，按兩下 [ **RTC 局部唯讀管理員**]。

4.  在 [ **RTC 本機唯讀系統管理員屬性**] 對話方塊中，按一下 [**新增**]。

5.  在 [**選取使用者、電腦、服務帳戶或群組**] 對話方塊中，按一下 [**位置**]。

6.  在 [**位置**] 對話方塊中，選取 [觀察程式] 節點電腦的名稱，然後按一下 **[確定]**。

7.  在 [**輸入要選取的物件名稱**] 方塊中，輸入 [**網路服務**]，然後按一下 **[確定]**。

8.  在 [ **RTC 本機唯讀系統管理員屬性**] 對話方塊中，按一下 **[確定**]，然後關閉 [**伺服器管理員**]。

重新開機觀察程式節點電腦。

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a>安裝觀察程式節點設定檔

在觀察程式節點電腦重新開機後，下一步就是執行檔案 Watchernode。 若要執行此檔案，請按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **lync server 2013**]，然後按一下 [ **lync Server Management shell**]，以開啟 Lync server 2013 管理命令介面。 在 Lync Server 管理命令介面中，輸入下列命令，然後按 ENTER （請確定並指定您 Watchernode 複本的實際路徑）：

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> 如先前所述，Watchernode 也可以從命令視窗執行。 若要開啟命令視窗，請按一下 [<STRONG>開始</STRONG>]，以滑鼠右鍵按一下 [<STRONG>命令提示</STRONG>字元]，然後按一下 [<STRONG>以系統管理員身分執行</STRONG>]。 當命令視窗開啟時，請輸入相同的命令，如先前所示。



</div>

當無法將觀察程式節點設定為受信任的應用程式池時，就會使用 [協商] 模式。 在此模式中，系統管理員必須在 [觀察程式] 節點上管理測試使用者密碼。

</div>

</div>

<span> </span>

</div>

</div>

</div>

