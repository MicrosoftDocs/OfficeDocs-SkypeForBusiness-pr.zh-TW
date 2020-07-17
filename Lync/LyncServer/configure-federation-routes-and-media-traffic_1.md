---
title: 設定同盟路由與媒體流量
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d6af77188809b092050629c1b74cdab8b20a2cc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754959"
---
# <a name="configure-federation-routes-and-media-traffic"></a>設定同盟路由與媒體流量

 


同盟是兩個或兩個以上 SIP 網域間的信任關係，其可允許不同組織中的使用者跨越網路界限進行通訊。 遷移至 Lync Server 2013 試驗集區之後，您必須從 Microsoft Office 通訊伺服器 2007 R2 Edge server 的同盟路由轉換為您的 Lync Server 2013 Edge server 的同盟路由。

請使用下列程式，將您 Office 通訊伺服器 2007 R2 Edge Server 和 Director 的同盟路由與媒體流量路由轉換至 Lync Server 2013 Edge Server，以進行單一網站部署。


> [!IMPORTANT]  
> 變更同盟路由與媒體流量路由需要您為 Lync Server 2013 和 Office 通訊伺服器 2007 R2 Edge server 排程維護停機時間。 這整個轉換過程同時也意味著，在運行中斷期間無法使用同盟存取。 您應該將停機時間排在您預期使用者活動最少的時間。 您也應該要提供足夠的通知給您的使用者。 請視情況規劃此運行中斷，並且在組織內設定適當的期望。




> [!IMPORTANT]  
> 如果舊版 Office 通訊伺服器 2007 R2 Edge Server 設定為使用 Access Edge service、Web 會議 Edge service 和 A/V Edge service 的相同 FQDN，則不支援此區段中的程式將同盟設定轉換為 Lync Server 2013 Edge Server。 如果舊版 Edge service 設定為使用相同的 FQDN，您必須先將所有使用者從 Office 通訊伺服器 2007 R2 遷移至 Lync Server 2013，然後在 Lync 2013 Server 的 [！] Edge Server 上啟用同盟，再解除委任 Office 通訊伺服器的 2007 R2 Edge Server。 如需詳細資料，請參閱下列主題： 
> <UL>
> <LI>
> <P><A href="move-remaining-users-to-lync-server-2013_1.md">將剩餘的使用者移至 Lync Server 2013</A></P>
> <LI>
> <P>「移除伺服器和伺服器角色」<A href="https://go.microsoft.com/fwlink/p/?linkid=268790">https://go.microsoft.com/fwlink/p/?LinkId=268790</A></P></LI></UL>




> [!IMPORTANT]  
> 如果您的 XMPP 同盟是透過 Lync Server 2013 Edge Server 路由傳送，舊版 Office 通訊伺服器 2007 R2 使用者將無法與 XMPP 同盟協力廠商通訊，除非所有使用者都已移至 Lync Server 2013、已設定 XMPP 原則和憑證，所以已在 Lync Server 2013 上設定 XMPP 同盟協力廠商，最後更新 DNS 專案。



若要在新增或移除伺服器角色時順利發行、啟用或停用拓撲，您應該以 RTCUniversalServerAdmins 和 Domain Admins 群組成員的使用者身分登入。 此外也可委派正確的使用者權限來新增伺服器角色。 如需詳細資訊，請參閱 Standard Edition server 或 Enterprise Edition server 部署檔中的[Lync server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。 若要進行其他組態變更，則僅需要 RTCUniversalServerAdmins 群組中的成員資格。

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>從 Lync Server 2013 網站移除舊版同盟關聯

1.  使用拓撲產生器，開啟試驗集區拓撲。

2.  在左窗格中，瀏覽至該站台節點。

3.  以滑鼠右鍵按一下站台，然後按一下 [編輯屬性]****。

4.  選取左窗格中的 [同盟路由]****。

5.  在 [網站同盟路由指派] 底下，清除 [**啟用 SIP 同盟**] 旁邊的核取方塊，以停用通過**BackCompatSite**的同盟路由。
    
    ![[編輯屬性] 對話方塊，同盟路由](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "[編輯屬性] 對話方塊，同盟路由")

6.  按一下 [確定]****，以關閉 [編輯屬性] 頁面。

7.  從 [**拓撲**產生器] 中，選取上方節點 [ **Lync Server**]。

8.  從 [**動作**] 功能表中，按一下 [**發行拓撲**]，然後完成嚮導。

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>將舊版 Edge Server 設定成非同盟 Edge Server

1.  從 [**拓撲**產生器] 的 [**動作**] 功能表中，按一下 [**合併 Office 通訊伺服器 2007 R2 拓撲**]。

2.  按 [下一步]**** 繼續。

3.  在 [指定 Edge 設定]**** 中，選取您目前設定以進行同盟的 [Edge Server 內部 FQDN]****，然後按一下 [變更]****。
    
    ![合併 OCS 2007 R2 拓撲，指定 Edge 設定](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "合併 OCS 2007 R2 拓撲，指定 Edge 設定")

4.  按 [下一步]**** 並接受預設值，直到抵達 [指定外部 Edge]**** 頁面為止：
    
    ![拓撲產生器的 [指定外部 Edge] 頁面](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "拓撲產生器的 [指定外部 Edge] 頁面")

5.  在 [指定外部 Edge]**** 中，清除 [此 Edge 集區是用於同盟和公用 IM 連線]**** 核取方塊。這樣就會移除與 BackCompatSite 的同盟關聯。
    

    > [!IMPORTANT]  
    > 此步驟非常重要。您必須清除這個選項，以移除舊版的同盟關聯。



6.  按 [下一步]**** 並接受精靈剩餘頁面的預設值。

7.  在 [摘要]**** 中按 [下一步]****，以開始合併拓撲。

8.  在 [**狀態**] 欄中，確認值為 [**成功**]，然後按一下 **[完成**] 以關閉嚮導。

9.  從 [**動作**] 功能表中，選取 [**發行拓撲**]，然後按 **[下一步]**。

10. 當 [發行精靈]**** 完成之後，按一下 [完成]****，以關閉精靈。
    
    ![在合併後顯示網站的拓撲產生器](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "在合併後顯示網站的拓撲產生器")
    
    如上圖所示，[**網站同盟路由指派**] 底下的**SIP 同盟**設定為 [**已停用**]。

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a>在 Lync Server 2013 Edge Server 上設定憑證

1.  從舊版 Office 通訊伺服器 2007 R2 Edge Server 匯出外部存取 Proxy 憑證與私密金鑰。

2.  在 Lync Server 2013 Edge Server 上，匯入上一個步驟中的 Access Proxy 外部憑證。

3.  將 Access Proxy 外部憑證指派給 Edge Server 的 Lync Server 2013 外部介面。

4.  不應變更 Lync Server 2013 Edge Server 的內部介面憑證。

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a>若要變更 Office 通訊伺服器 2007 R2 同盟路由以使用 Lync Server 2013 Edge Server

1.  在 Office 通訊伺服器 2007 R2 Standard Edition server 或前端伺服器上，開啟 Office 通訊伺服器 2007 R2 系統管理工具。

2.  在左窗格中，展開頂端節點，以滑鼠右鍵按一下 [樹系]**** 節點。選取 [內容]****，然後按一下 [通用內容]****。

3.  按一下 [同盟]**** 索引標籤。

4.  選取核取方塊以啟用同盟與公用 IM 連線。

5.  輸入 Lync Server 2013 Edge Server 的 FQDN，然後按一下 **[確定]**。
    
    ![OCS 全域屬性，[同盟] 索引標籤](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS 全域屬性，[同盟] 索引標籤")

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>開啟 Lync Server 2013 Edge Server federation

1.  在 [拓撲產生器] 的左窗格中，流覽至 [Lync Server 2013 **Edge pool** ] 節點。

2.  展開節點，再以滑鼠右鍵按一下所列出的 Edge Server，然後按一下 [編輯屬性]****。
    

    > [!NOTE]  
    > 只可對單一 Edge 集區啟用同盟。 如果您有多個 Edge 集區，請選取其中一個做為同盟 Edge 集區。



3.  選取 [一般]**** 頁面的 [啟用此 Edge 集區的同盟 (連接埠 5061)]**** 核取方塊。
    
    ![編輯內容，一般，啟用 Edge Federation](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "編輯內容，一般，啟用 Edge Federation")

4.  按一下 [確定]****，以關閉 [編輯屬性] 頁面。

5.  然後，瀏覽至站台節點。

6.  以滑鼠右鍵按一下站台，然後按一下 [編輯屬性]****。

7.  在左窗格中，按一下 [同盟路由]****。

8.  在 [**網站同盟路由指派**] 底下，選取 [**啟用 SIP 同盟**]，然後從清單中選取所列的 Lync server 2013 Edge Server。

9.  按一下 [確定]**** 關閉 [編輯內容]**** 頁面。
    
    ![編輯內容，一般，關聯 Edge 集區](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "編輯內容，一般，關聯 Edge 集區")
    
    如有部署多個站台，請逐一在各個站台上完成此程序。

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>設定 Lync Server 2013 Edge Server 輸出媒體路徑

1.  在 [**拓撲**產生器] 中，流覽至 [ **Standard Edition 前端伺服器**] 或 [ **Enterprise edition 前端**集區] 底下的 [Lync Server 2013 集區]。

2.  以滑鼠右鍵按一下集區，然後按一下 [編輯屬性]****。

3.  選取 [關聯]**** 區段底下的 [關聯 Edge 集區 (適用於媒體元件)]**** 核取方塊。

4.  從下拉式清單方塊中，選取 [Lync Server 2013 Edge Server]。
    
    ![[編輯屬性] 對話方塊，關聯 Edge 集區](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "[編輯屬性] 對話方塊，關聯 Edge 集區")

5.  按一下 [確定]**** 關閉 [編輯內容]**** 頁面。

## <a name="to-publish-edge-server-configuration-changes"></a>發行 Edge Server 的設定變更

1.  從 [**拓撲**產生器] 中，選取上方節點 [ **Lync Server**]。

2.  從 [動作]**** 功能表中，選取 [發行拓撲]****，然後完成精靈。

3.  等候部署中所有集區的 Active Directory 複寫作業開始。
    

    > [!NOTE]  
    > 您將會見到下列訊息：<BR><STRONG>警告：拓撲包含多個同盟 Edge Server。移轉至最新版本的產品時可能會發生此問題。在這個情況下，僅會啟動一個 Edge Server 以主動用於同盟。請確認外部 DNS SRV 記錄有指向正確的 Edge Server。若您想同時部署多部主動的同盟 Edge Server (亦即，不是在移轉案例中)，請確認所有同盟協力廠商都是使用 Office Communications Server 2007 R2 或 Lync Server，並確認外部 DNS SRV 記錄有提列所有啟用同盟的 Edge Servers。</STRONG><BR>此為預期中的警告，可以不予理會。



## <a name="to-verify-federation-and-remote-access-for-external-users"></a>確認外部使用者的同盟及遠端存取

1.  在 Lync Server 2013 前端伺服器上，開啟 Lync Server 管理命令介面。

2.  若要確認同盟及遠端存取的狀態，請從命令列輸入下列命令：
    
        Get-CsAccessEdgeConfiguration

3.  若要啟用同盟和遠端存取，請在命令列中輸入下列命令：
    
        Set-CsAccessEdgeConfiguration
    
    如需這些 Cmdlet 的詳細資訊，請參閱下列主題： [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg398574\(v=ocs.15\))和[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg413017\(v=ocs.15\))。

4.  請等到複寫完成後，才能讓 Lync Server 2013 Edge server 成為線上，並測試同盟與外部存取。

## <a name="to-configure-lync-server-2013-edge-server"></a>設定 Lync Server 2013 Edge Server

1.  讓所有的 Lync Server 2013 Edge server 線上。

2.  更新外部防火牆路由規則或硬體負載平衡器設定，以將外部存取（通常是埠443）及同盟（通常是埠5061）的 SIP 流量傳送至 Lync Server 2013 Edge Server，而不是使用舊版 Edge Server。
    

    > [!NOTE]  
    > 如果您沒有硬體負載平衡器，則必須更新同盟的 DNS A 記錄，以解析新的 Lync Server Access Edge server。 若要達到最低的中斷，請減少外部 Lync Server Access Edge FQDN 的 TTL 值，以便在更新 DNS 以指向新的 Lync Server Access Edge server 時，會快速更新同盟和遠端存取。



3.  接下來，停止每台 Edge Server 電腦的**Lync Server Access Edge** 。

4.  從每個舊版 Edge Server 電腦上，從 [系統**管理工具**] 中開啟 [**服務**] 小程式。

5.  在服務清單中，尋找 [Office Communications Server Access Edge]****。

6.  以滑鼠右鍵按一下服務名稱，然後選取 [停止]**** 停止服務。

7.  將 [啟動類型] 設為 [停用]****。

8.  按一下 [確定]****，以關閉 [屬性]**** 視窗。

## <a name="to-test-connectivity-of-external-users-and-external-access"></a>測試外部使用者與外部存取的連線能力

  - 至少一個同盟網域的使用者、Lync Server 2013 上的內部使用者，以及 Office 通訊伺服器 2007 R2 上的使用者。 測試立即訊息 (IM)、目前狀態、音訊/視訊 (A/V) 及桌面共用。

  - 您的組織支援的每個公用 IM 服務提供者（及布建已完成）的使用者，與 Lync Server 2013 上的使用者和 Office 通訊伺服器 2007 R2 上的使用者進行通訊。

  - 確認匿名使用者可以加入會議。

  - 使用遠端使用者存取（從內部網路外部（但不含 VPN）2007登錄 office 通訊伺服器 2007 R2 的使用者，與 Lync Server 2013 上的使用者，以及 Office 通訊伺服器 2007 R2 上的使用者。 測試 IM、目前狀態、A/V 及桌面共用。

  - 在 lync server 2013 上主控的使用者，該使用者是在 lync server 2013 上使用遠端使用者存取（從內部網路以外的地方登入 Lync Server 2013），以及 Office 通訊伺服器 2007 R2 上的使用者。 測試 IM、目前狀態、A/V 及桌面共用。

