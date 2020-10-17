---
title: 設定同盟路由與媒體流量
description: 設定同盟路由與媒體流量。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49733720
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de26f472bddc504ff79e427b5243587f27020c3d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542979"
---
# <a name="configure-federation-routes-and-media-traffic"></a>設定同盟路由與媒體流量

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-15_

同盟是兩個或兩個以上 SIP 網域間的信任關係，其可允許不同組織中的使用者跨越網路界限進行通訊。 遷移至 Lync Server 2013 試驗集區之後，您必須從 Lync server 2010 Edge server 的同盟路由轉換為您的 Lync Server 2013 Edge server 的同盟路由。

請使用下列程式，將 Lync Server 2010 Edge Server 和 Director 的同盟路由與媒體流量路由轉換至 Lync Server 2013 Edge Server，以進行單一網站部署。

<div>


> [!IMPORTANT]  
> 變更同盟路由與媒體流量路由需要您為 Lync Server 2013 和 Lync Server 2010 Edge Server 排定維護停機時間。 這整個轉換過程同時也意味著，在運行中斷期間無法使用同盟存取。 您應該將停機時間排在您預期使用者活動最少的時間。 您也應該要提供足夠的通知給您的使用者。 請視情況規劃此運行中斷，並且在組織內設定適當的期望。



</div>

<div>


> [!IMPORTANT]  
> 如果舊版 Lync Server 2010 Edge Server 設定為使用 Access Edge service、Web 會議 Edge service 和 A/V Edge service 的相同 FQDN，則不支援本節中的程式。 如果舊版 Edge service 設定為使用相同的 FQDN，您必須先將所有使用者從 Lync Server 2010 遷移至 Lync Server 2013，然後在 2013 Lync server 的 [！] Edge Server 上啟用同盟之前解除委任 Lync Server 2010 Edge Server。



</div>

<div>


> [!IMPORTANT]  
> 如果您的 XMPP 同盟是透過 Lync Server 2013 Edge Server 路由傳送，舊版 Lync Server 2010 使用者將無法與 XMPP 同盟協力廠商通訊，除非所有使用者都已移至 Lync Server 2013、已設定 XMPP 原則和憑證，所以已在 Lync Server 2013 上設定 XMPP 同盟協力廠商，最後更新 DNS 專案。



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>從 Lync Server 2013 網站移除舊版同盟關聯

1.  在 Lync Server 2013 前端伺服器上，在拓撲產生器中開啟現有的拓撲。

2.  在左窗格中，流覽至 [ **Lync Server**] 正下方的 [網站] 節點。

3.  以滑鼠右鍵按一下網站，然後按一下 [ **編輯屬性**]。

4.  在左窗格中，選取 [ **同盟路由**]。

5.  在 [ **網站同盟路由指派**] 底下，清除 [ **啟用 SIP 同盟** ] 核取方塊，以停用透過舊版 Lync Server 2010 環境的同盟路由。
    
    ![[編輯屬性] 對話方塊，[同盟路由] 頁面](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "[編輯屬性] 對話方塊，[同盟路由] 頁面")

6.  按一下 [確定]****，以關閉 [編輯屬性] 頁面。

7.  從 [ **拓撲**產生器] 中，選取上方節點 [ **Lync Server**]。

8.  從 [ **動作** ] 功能表中，按一下 [ **發行拓撲**]。

9.  按 **[下一步]** 完成發佈程式，然後在發佈程式完成時按一下 **[完成]** 。

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>將舊版 Edge Server 設定成非同盟 Edge Server

1.  在左窗格中，流覽至 [ **Lync Server 2010** ] 節點，然後流覽至 [ **Edge** 集區] 節點。

2.  以滑鼠右鍵按一下 Edge server，然後按一下 [ **編輯屬性**]。

3.  在左窗格中選取 **[一般** ]。

4.  清除 [ **啟用此 Edge 集區的同盟 (埠 5061) ** ] 核取方塊專案，然後選取 **[確定]** 以關閉頁面。
    
    ![編輯內容，一般，清除啟用同盟](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "編輯內容，一般，清除啟用同盟")

5.  從 [ **動作** ] 功能表中，選取 [ **發行拓撲**]，然後按 **[下一步]**。

6.  當 [發行精靈]**** 完成之後，按一下 [完成]****，以關閉精靈。

7.  驗證舊版 Edge server 的同盟功能已停用。
    
    ![拓撲產生器，Edge 集區，已停用同盟](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "拓撲產生器，Edge 集區，已停用同盟")

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a>在 Lync Server 2010 Edge Server 上設定憑證

1.  從舊版 Lync Server 2010 Edge Server 匯出外部存取 Proxy 憑證及私密金鑰。

2.  在 Lync Server 2013 Edge Server 上，匯入上一個步驟中的 Access Proxy 外部憑證。

3.  將 Access Proxy 外部憑證指派給 Edge Server 的 Lync Server 2013 外部介面。

4.  Lync Server 2013 Edge Server 的內部介面憑證應從受信任的 CA 要求並被指派。

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a>若要變更 Lync Server 2010 同盟路由以使用 Lync Server 2013 Edge Server

1.  在 [拓撲產生器] 的左窗格中，流覽至 [ **Lync Server 2013** ] 節點，然後流覽至 [ **Edge** 集區] 節點。

2.  以滑鼠右鍵按一下 Edge server，然後按一下 [ **編輯屬性**]。

3.  在左窗格中選取 **[一般** ]。

4.  選取 [ **啟用此 Edge 集 ** 區的同盟] 的核取方塊專案 (埠 5061) 然後按一下 **[確定]** 以關閉頁面。
    
    ![[編輯屬性] 對話方塊，[一般] 頁面](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "[編輯屬性] 對話方塊，[一般] 頁面")

5.  從 [ **動作** ] 功能表中，選取 [ **發行拓撲**]，然後按 **[下一步]**。

6.  當 [發行精靈]**** 完成之後，按一下 [完成]****，以關閉精靈。

7.  驗證 **同盟 (埠 5061) ** 設定為 [ **啟用**]。
    
    ![拓撲產生器，Edge 集區，啟用同盟](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "拓撲產生器，Edge 集區，啟用同盟")

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a>更新 Lync Server 2013 Edge Server 同盟的下一個躍點

1.  在 [拓撲產生器] 的左窗格中，流覽至 [ **Lync Server 2013** ] 節點，然後流覽至 [ **Edge** 集區] 節點。

2.  展開節點，再以滑鼠右鍵按一下所列出的 Edge Server，然後按一下 [編輯屬性]****。

3.  在 [ **一般** ] 頁面的 **[下一個躍點選取範圍]** 下，從下拉式清單中選取 [Lync Server 2013 集區]。
    
    ![[編輯屬性] 對話方塊，[下一個躍點] 頁面](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "[編輯屬性] 對話方塊，[下一個躍點] 頁面")

4.  按一下 [確定]****，以關閉 [編輯屬性] 頁面。

5.  從 [ **拓撲**產生器] 中，選取上方節點 [ **Lync Server** ]。

6.  從 [ **動作** ] 功能表中，按一下 [ **發行拓撲** ]，然後完成嚮導。

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>設定 Lync Server 2013 Edge Server 輸出媒體路徑

1.  在 [拓撲產生器] 的左窗格中，流覽至 [ **Lync Server 2013** ] 節點，然後流覽至 [ **Standard edition 前端伺服器** ] 或 [ **Enterprise edition 前端**集區] 底下的集區。

2.  以滑鼠右鍵按一下集區，然後按一下 [編輯屬性]****。

3.  選取 [關聯]**** 區段底下的 [關聯 Edge 集區 (適用於媒體元件)]**** 核取方塊。
    
    ![編輯內容，一般，關聯 Edge 集區](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "編輯內容，一般，關聯 Edge 集區")

4.  從下拉式清單方塊中，選取 [Lync Server 2013 Edge Server]。

5.  按一下 [確定]**** 關閉 [編輯內容]**** 頁面。

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>開啟 Lync Server 2013 Edge Server federation

1.  在 [拓撲產生器] 的左窗格中，流覽至 [ **Lync Server 2013** ] 節點，然後流覽至 [ **Edge** 集區] 節點。

2.  展開節點，再以滑鼠右鍵按一下所列出的 Edge Server，然後按一下 [編輯屬性]****。
    
    <div>
    

    > [!NOTE]  
    > 只可對單一 Edge 集區啟用同盟。 如果您有多個 Edge 集區，請選取其中一個做為同盟 Edge 集區。

    
    </div>

3.  在 [ **一般** ] 頁面上，確認已選取 [ **啟用此 Edge 集區的同盟 (埠 5061) ** 設定]。
    
    ![[編輯屬性] 對話方塊，[一般] 頁面](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "[編輯屬性] 對話方塊，[一般] 頁面")

4.  按一下 [確定]****，以關閉 [編輯屬性] 頁面。

5.  然後，瀏覽至站台節點。

6.  以滑鼠右鍵按一下站台，然後按一下 [編輯屬性]****。

7.  在左窗格中，按一下 [同盟路由]****。

8.  在 [ **網站同盟路由指派**] 底下，選取 [ **啟用 SIP 同盟**]，然後從清單中選取所列的 Lync server 2013 Edge Server。
    
    ![編輯屬性、同盟路由頁面](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "編輯屬性、同盟路由頁面")

9.  按一下 **[確定]** 關閉 **[編輯內容]** 頁面。
    
    如有部署多個站台，請逐一在各個站台上完成此程序。

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a>發行 Edge Server 的設定變更

1.  從 [ **拓撲**產生器] 中，選取上方節點 [ **Lync Server** ]。

2.  從 [動作]**** 功能表中，選取 [發行拓撲]****，然後完成精靈。

3.  等候部署中所有集區的 Active Directory 複寫作業開始。
    
    <div>
    

    > [!NOTE]  
    > 您將會見到下列訊息：<BR><STRONG>警告：此拓撲包含一個以上的同盟 Edge Server。這可能會在將產品遷移至較新版本的產品時發生。在此情況下，只有一部 Edge Server 會積極用於同盟。驗證外部 DNS SRV 記錄是否指向正確的 Edge Server。如果您想要將多個同盟 Edge Server 同時部署為作用中 (也就是說，不是遷移案例) ，請確認所有同盟協力廠商都在使用 Lync Server。驗證外部 DNS SRV 記錄是否列出所有啟用同盟的 Edge Server。</STRONG><BR>此為預期中的警告，可以不予理會。

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a>設定 Lync Server 2013 Edge Server

1.  讓所有的 Lync Server 2013 Edge server 線上。

2.  更新外部防火牆路由規則或硬體負載平衡器設定，以傳送外部存取 (的 SIP 流量，通常是埠 443) 和同盟 (的埠 5061) 至 Lync Server 2013 Edge Server，而不是舊版 Edge Server。
    
    <div>
    

    > [!NOTE]  
    > 如果您沒有硬體負載平衡器，則需要更新同盟的 DNS A 記錄，以解析為新的 Lync Server Access Edge server。 若要達到最低的中斷，請縮小外部 Lync Server Access Edge FQDN 的 TLL 值，以便在更新 DNS 以指向新的 Lync Server Access Edge 時，會快速更新同盟和遠端存取。

    
    </div>

3.  接下來，停止每台 Edge Server 電腦的 **Lync Server Access Edge** 。

4.  從每個舊版 Edge Server 電腦上，從 [系統**管理工具**] 中開啟 [**服務**] 小程式。

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

