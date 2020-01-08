---
title: Lync Server 2013：Lync VDI 外掛程式先決條件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync VDI plug-in prerequisites
ms:assetid: da25a976-7624-4dfc-b332-9c4db4ee78da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205304(v=OCS.15)
ms:contentKeyID: 48185552
ms.date: 03/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae32480e5a3dbfbdfc22c4dbde59c62383c9587f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976720"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a>Lync Server 2013 中的 Lync VDI 外掛程式先決條件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017-03-07_

在虛擬桌面基礎結構（VDI）環境中，虛擬機器與使用者的本機電腦必須符合本節中所述的需求。

<div>


> [!NOTE]  
> 如需有關如何安裝及部署虛擬化環境的詳細資訊，請參閱您的虛擬化解決方案提供者。 如需有關根據 Hyper-v 和遠端桌面服務部署虛擬化環境的相關資訊，請參閱 Microsoft TechNet 文件庫中的下列文章： 
> <UL>
> <LI>
> <P>Hyper-v<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></P>
> <LI>
> <P>Windows Server&nbsp;2008&nbsp;R2 中的遠端桌面服務<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></P></LI></UL>



</div>

下列是在資料中心電腦上執行的虛擬機器需求：

  - 虛擬機器必須使用 Windows 10、Windows 8.1、Windows 8、Windows 7 或 Windows Server 2008 R2 （含最新的 service pack）進行設定。

以下是使用者與使用者的本機電腦需求：

  - 使用者必須駐留在 Lync Server 2013。

  - 本機電腦必須執行 Windows Embedded Standard 7 （含 SP1）、Windows 7 （含 SP1）、windows 8、Windows 8.1 Embedded 或 Windows 8.1 （未內嵌）。

  - 如果您使用的是遠端桌面服務，Lync VDI 外掛程式位數（也就是應用程式是32位或64位）必須符合本機電腦的作業系統位數。 本機電腦上的作業系統與虛擬機器上作業系統的位數不需要相符。 如果您使用的是其他虛擬化解決方案或平臺，請參閱虛擬化解決方案供應商關於位數需求的指導方針。

  - 本機電腦必須執行最新版本的遠端桌面用戶端。 從您的虛擬化方案提供者，從 Microsoft 或最新的遠端桌面用戶端軟體，安裝遠端桌面服務用戶端的最新更新。 如需最新的遠端桌面服務更新[https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)，請參閱。

  - 在本機電腦上，必須設定遠端桌面用戶端設定，以便在本機電腦上播放音訊，並停用遠端錄製。 若要在 Windows 中設定遠端桌面連線的這些設定，請參閱下一節「設定遠端桌面連線設定」。

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a>設定遠端桌面連線設定

若要在 Windows 中為 Lync VDI 外掛程式準備遠端桌面連線，請依照下列步驟進行。

1.  如果本機電腦執行的是 Windows 8，請略過此步驟。 如果本機電腦執行的是 Windows 7 與 SP1，請安裝最新的 Windows 8 版的遠端桌面服務用戶端， [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)網址為。

2.  按一下 [**開始**]，然後按一下 [**遠端桌面**連線]，啟動遠端桌面服務用戶端。

3.  按一下 [**選項**]。

4.  按一下 [**本機資源**] 索引標籤。在 [**遠端音訊**] 底下，按一下 [**設定**]，然後執行下列動作：
    
      - 在 [**遠端音訊播放**] 底下，選取 [**在這台電腦上播放**]。
    
      - 在 [**遠端音訊錄製**] 底下，選取 [不**錄製**]。
    
      - 按一下 [確定]****。

5.  按一下 [**體驗**] 索引標籤。在 [**效能**] 底下，清除 [**永久點陣圖緩存**] 核取方塊。

6.  按一下 [**一般**] 索引標籤。在 [**電腦**] 中，輸入虛擬機器的名稱，然後按一下 **[連線]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

