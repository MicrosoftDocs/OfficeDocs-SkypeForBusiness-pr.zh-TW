---
title: 設定同盟路由及媒體流量
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49733720
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f3382df255f4fb9422df38efbf6cf1a3d5d522f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-federation-routes-and-media-traffic"></a>設定同盟路由及媒體流量

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012 年 10 月 15_

同盟是兩個或兩個以上 SIP 網域間的信任關係，其可允許不同組織中的使用者跨越網路界限進行通訊。 在移轉至 Lync Server 2013 試驗集區之後，您需要轉換的 Lync Server 2013 Edge Server 同盟路由至 Lync Server 2010 Edge Server 同盟路由。

使用下列程序來轉換的同盟路由與媒體流量路由從您的 Lync Server 2010 Edge Server 和 Director 至 Lync Server 2013 Edge Server，進行單一站台部署。

<div>


> [!IMPORTANT]  
> 變更同盟路由與媒體流量路由需要您排程維護停機時間的 Lync Server 2013 和 Lync Server 2010 Edge Server。 這整個轉換過程同時也意味著，在運行中斷期間無法使用同盟存取。 您應該將停機時間排在您預期使用者活動最少的時間。 您也應該要提供足夠的通知給您的使用者。 請視情況規劃此運行中斷，並且在組織內設定適當的期望。



</div>

<div>


> [!IMPORTANT]  
> 如果您舊版 Lync Server 2010 Edge Server 設定為相同的 FQDN 用於 Access Edge service、 Web 會議 Edge 服務和 A / V Edge service] 本節中的程序不受支援。 如果舊版 Edge service 設定為使用相同的 FQDN，您必須先將所有使用者從 Lync Server 2010 都移轉至 Lync Server 2013 中，然後解除委任 Lync Server 2010 Edge Server，才能啟用 Lync Server 2013 Edge Server 上的同盟。



</div>

<div>


> [!IMPORTANT]  
> 如果您的 XMPP 同盟透過 Lync Server 2013 Edge Server 路由傳送，舊版 Lync Server 2010 使用者將無法與 XMPP 同盟協力廠商進行通訊，直到所有使用者已都移至 Lync Server 2013 XMPP 原則與憑證都已設定，已在 Lync Server 2013 設定 XMPP 同盟協力廠商，最後已更新 DNS 項目。



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>若要從 Lync Server 2013 網站移除舊版同盟關聯

1.  在 Lync Server 2013 前端伺服器上，請在拓撲產生器開啟現有的拓撲。

2.  在左窗格中，瀏覽至位於**Lync Server**的正下方的 [網站] 節點。

3.  在網站上按一下滑鼠右鍵，然後按一下 [**編輯內容]**。

4.  在左窗格中，選取 [**同盟路由**]。

5.  [**網站同盟路由指派**]，清除 [**啟用 SIP 同盟**] 核取方塊，以停用透過舊版 Lync Server 2010 環境的同盟路由。
    
    ![編輯內容] 對話方塊中，同盟路由] 頁面](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "編輯內容] 對話方塊中，同盟路由] 頁面")

6.  按一下 [確定]****，以關閉 [編輯屬性] 頁面。

7.  從**拓撲產生器中**，選取頂端節點 [ **Lync Server**。

8.  從 [**動作**] 功能表中，按一下 [**發行拓撲**]。

9.  按一下 [**下一步**以完成發行程序，然後在發行程序完成時，按一下 [**完成**]。

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>將舊版 Edge Server 設定成非同盟 Edge Server

1.  在左窗格中，瀏覽至 [ **Lync Server 2010** ] 節點，然後至 [ **Edge 集區**] 節點。

2.  以滑鼠右鍵按一下 Edge server]，然後按一下 [**編輯內容]**。

3.  在左窗格中，選取 [**一般**]。

4.  清除 [**啟用此 Edge 集區 （連接埠 5061） 的同盟**] 核取方塊項目，然後選取 **[確定]** 以關閉頁面。
    
    ![編輯內容]，一般] 上，清除 [啟用同盟](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "編輯內容]，一般] 上，清除 [啟用同盟")

5.  從 [**動作**] 功能表中，選取 [**發行拓撲**，，然後按一下 [**下一步**。

6.  當 [發行精靈]**** 完成之後，按一下 [完成]****，以關閉精靈。

7.  確認舊版 edge server 已停用同盟。
    
    ![拓撲產生器] 中的 Edge 集區、 停用同盟](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "拓撲產生器] 中的 Edge 集區、 停用同盟")

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a>在 Lync Server 2010 Edge Server 上設定憑證

1.  匯出 Access Proxy 外部憑證與私密金鑰，從舊版的 Lync Server 2010 Edge Server。

2.  Lync Server 2013 Edge Server 上匯入上一個步驟的 Access Proxy 外部憑證。

3.  將 Access Proxy 外部憑證指派給 Lync Server 2013 Edge server 外部介面。

4.  Lync Server 2013 Edge Server 的內部介面憑證應該從信任的 CA 要求，並指派。

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a>若要變更 Lync Server 2010 同盟路由以使用 Lync Server 2013 Edge Server

1.  從拓撲產生器] 左窗格中，瀏覽至 [ **Lync Server 2013** ] 節點，然後至 [ **Edge 集區**] 節點。

2.  以滑鼠右鍵按一下 Edge server]，然後按一下 [**編輯內容]**。

3.  在左窗格中，選取 [**一般**]。

4.  選取 [**啟用此 Edge 集區 （連接埠 5061） 的同盟**] 核取方塊項目，然後按一下 [關閉] 頁面的 **[確定]** 。
    
    ![編輯內容] 對話方塊中，[一般] 頁面](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "編輯內容] 對話方塊中，[一般] 頁面")

5.  從 [**動作**] 功能表中，選取 [**發行拓撲**，，然後按一下 [**下一步**。

6.  當 [發行精靈]**** 完成之後，按一下 [完成]****，以關閉精靈。

7.  確認**同盟 （連接埠 5061）** 設為 [**已啟用**]。
    
    ![拓撲產生器] 中 [Edge 集區，同盟啟用](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "拓撲產生器] 中 [Edge 集區，同盟啟用")

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a>更新 Lync Server 2013 Edge Server 同盟的下一個躍點

1.  從拓撲產生器] 左窗格中，瀏覽至 [ **Lync Server 2013** ] 節點，然後至 [ **Edge 集區**] 節點。

2.  展開節點，再以滑鼠右鍵按一下所列出的 Edge Server，然後按一下 [編輯屬性]****。

3.  在 [**一般**] 頁面的 [**下一個躍點選取範圍**，從下拉式清單選取 Lync Server 2013 集區。
    
    ![編輯內容] 對話方塊中下, 一個躍點] 頁面上](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "編輯內容] 對話方塊中下, 一個躍點] 頁面上")

4.  按一下 [確定]****，以關閉 [編輯屬性] 頁面。

5.  從**拓撲產生器中**，選取頂端節點 [ **Lync Server** 。

6.  從 [**動作**] 功能表中，按一下 [**發行拓撲**，然後完成精靈。

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>若要設定 Lync Server 2013 Edge Server 輸出媒體路徑

1.  從拓撲產生器] 左窗格中，瀏覽至 [ **Lync Server 2013** ] 節點，然後再到**Standard Edition 前端伺服器**或**Enterprise Edition 前端集區]** 下方的集區。

2.  以滑鼠右鍵按一下集區，然後按一下 [編輯屬性]****。

3.  選取 [關聯]**** 區段底下的 [關聯 Edge 集區 (適用於媒體元件)]**** 核取方塊。
    
    ![編輯內容]，一般而言，關聯 Edge 集區](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "編輯內容]，一般而言，關聯 Edge 集區")

4.  從下拉式清單方塊中，選取 [Lync Server 2013 Edge Server。

5.  按一下 [確定]**** 關閉 [編輯內容]**** 頁面。

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>開啟 Lync Server 2013 Edge Server 同盟

1.  從拓撲產生器] 左窗格中，瀏覽至 [ **Lync Server 2013** ] 節點，然後至 [ **Edge 集區**] 節點。

2.  展開節點，再以滑鼠右鍵按一下所列出的 Edge Server，然後按一下 [編輯屬性]****。
    
    <div>
    

    > [!NOTE]  
    > 單一 Edge 集區時，可以只啟用同盟。 如果您有多個 Edge 集區，請選取其中一個做為同盟 Edge 集區。

    
    </div>

3.  在 [**一般**] 頁面上，確認已選取 [**啟用此 Edge 集區 (連接埠 5061) 的同盟**] 設定。
    
    ![編輯內容] 對話方塊中，[一般] 頁面](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "編輯內容] 對話方塊中，[一般] 頁面")

4.  按一下 [確定]****，以關閉 [編輯屬性] 頁面。

5.  然後，瀏覽至站台節點。

6.  以滑鼠右鍵按一下站台，然後按一下 [編輯屬性]****。

7.  在左窗格中，按一下 [同盟路由]****。

8.  在 [**網站同盟路由指派**]，選取 [**啟用 SIP 同盟**]，然後從清單中選取 [列出 Lync Server 2013 Edge Server。
    
    ![編輯同盟路由] 頁面上的屬性](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "編輯同盟路由] 頁面上的屬性")

9.  按一下 **[確定]** 關閉 **[編輯內容]** 頁面。
    
    如有部署多個站台，請逐一在各個站台上完成此程序。

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a>發行 Edge Server 的設定變更

1.  從**拓撲產生器中**，選取頂端節點 [ **Lync Server** 。

2.  從 [動作]**** 功能表中，選取 [發行拓撲]****，然後完成精靈。

3.  等候部署中所有集區的 Active Directory 複寫作業開始。
    
    <div>
    

    > [!NOTE]  
    > 您將會見到下列訊息：<BR><STRONG>警告： 拓撲包含多個同盟的 Edge Server。這可能會發生期間遷移至較新版本的產品。在此情況下，您會主動同盟使用只有一部 Edge Server。確認外部 DNS SRV 記錄會指向正確的 Edge Server。如果您想要部署多個同盟 Edge Server 可同時作用中 （也就是未移轉案例中），請確認所有的同盟協力廠商使用 Lync Server。確認外部 DNS SRV 記錄會列出所有已啟用同盟 Edge Server。</STRONG><BR>此為預期中的警告，可以不予理會。

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a>若要設定 Lync Server 2013 Edge Server

1.  將所有 Lync Server 2013 Edge server 上線。

2.  更新外部防火牆的路由規則或硬體負載平衡器設定傳送外部存取的 SIP 流量 （通常是連接埠 443） 及同盟 （通常是連接埠 5061） 至 Lync Server 2013 Edge Server，而不是舊版 Edge Server。
    
    <div>
    

    > [!NOTE]  
    > 如果您不具備硬體負載平衡器，您需要更新來解析至新的 Lync Server Access Edge server 同盟的 DNS A 記錄。 若要達成此目的使用最小中斷，減少 TLL 值外部的 Lync Server Access Edge fqdn，以便當 DNS 以指向新的 Lync Server Access Edge 更新時，同盟與遠端存取會快速更新。

    
    </div>

3.  接下來，停止**Lync Server Access Edge** ] 每個 Edge Server 的電腦。

4.  從每部舊版的 Edge Server 電腦，開啟**系統管理工具]**[**服務**] 小程式。

5.  在 [服務] 清單中，尋找 [ **Lync Server Access Edge**]。

6.  以滑鼠右鍵按一下服務名稱，然後選取 [停止]**** 停止服務。

7.  將 [啟動類型] 設為 [停用]****。

8.  按一下 [確定]****，以關閉 [屬性]**** 視窗。

</div>

</div>

<span> </span>

</div>

</div>

</div>

