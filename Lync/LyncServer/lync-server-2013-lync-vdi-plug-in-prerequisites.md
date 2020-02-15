---
title: 'Lync Server 2013: Lync VDI 外掛程式先決條件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync VDI plug-in prerequisites
ms:assetid: da25a976-7624-4dfc-b332-9c4db4ee78da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205304(v=OCS.15)
ms:contentKeyID: 48185552
ms.date: 03/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1e5434ed445bf19d2aaeea146ba0edb7dcac04c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a>Lync Server 2013 中的 Lync VDI 外掛程式先決條件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017年-03-07_

在虛擬桌面基礎結構 (VDI) 環境中，虛擬機器與使用者的本機電腦必須符合本節所述的需求。

<div>


> [!NOTE]  
> 您的虛擬化解決方案提供者，如需如何安裝及部署虛擬化的環境的詳細資訊，請參閱。 如需部署虛擬化的環境根據 HYPER-V 與遠端桌面服務的資訊，請參閱 Microsoft TechNet Library 中的下列文章： 
> <UL>
> <LI>
> <P>Hyper-v 在<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></P>
> <LI>
> <P>在 Windows Server 中的遠端桌面服務&nbsp;2008年&nbsp;在 R2<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></P></LI></UL>



</div>

資料中心電腦上執行的虛擬機器的需求如下：

  - 虛擬機器必須使用最新的 service pack 設定與 Windows 10、 Windows 8.1、 Windows 8、 Windows 7 或 Windows Server 2008 R2。

使用者和使用者的本機電腦的需求如下：

  - 使用者必須位於 Lync Server 2013。

  - 本機電腦必須執行 Windows Embedded Standard 7 SP1、 Windows 7 SP1、 Windows 8、 Windows 8.1 內嵌，或 Windows 8.1 （不內嵌）。

  - 如果您使用遠端桌面服務，Lync VDI 外掛程式位元 （也就是應用程式是否 32 位元或 64 位元） 必須符合本機電腦的作業系統位元。 比對不需要在本機電腦上的 operating system 和虛擬機器上的作業系統的位元。 如果您使用另一個虛擬化解決方案或平台，從您的虛擬化解決方案提供者元之需求的相關參考指南。

  - 本機電腦必須執行最新版的遠端桌面用戶端。 從您的虛擬化解決方案提供者安裝來自 Microsoft 的遠端桌面服務用戶端的最新的更新或最新的遠端桌面用戶端軟體。 如需最新的遠端桌面服務更新，請參閱[https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)。

  - 本機電腦上，以便在本機電腦上播放音訊，並停用遠端錄製必須設定的遠端桌面用戶端設定。 若要在 Windows 中設定這些設定的遠端桌面連線，請參閱下一步] 區段中，「 若要設定遠端桌面連線設定 >。

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a>若要設定遠端桌面連線設定

若要準備 Lync VDI 外掛程式 Windows 中的遠端桌面連線，請遵循下列步驟。

1.  如果本機電腦執行 Windows 8，略過此步驟。 如果本機電腦執行 Windows 7 sp1，安裝在 Windows 8 新版的遠端桌面服務用戶端，可在[https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)。

2.  按一下 [**開始**]，然後按一下 [**遠端桌面連線**來啟動遠端桌面服務用戶端。

3.  按一下 **[選項]**。

4.  按一下 [**本機資源**] 索引標籤。在 [**遠端音效**] 下按一下 [**設定**]，然後執行下列動作：
    
      - 在 [**遠端音效播放**下, 選取 [**此電腦上播放**]。
    
      - 在 [**遠端音效錄製**] 下選取 [**不錄製]**。
    
      - 按一下 [確定]****。

5.  按一下 [**經驗**] 索引標籤。在 [**效能**] 下清除**常設點陣圖快取**] 核取方塊。

6.  按一下 [**一般**] 索引標籤。在**電腦**上，輸入在虛擬機器的名稱，然後按一下 [**連線**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

