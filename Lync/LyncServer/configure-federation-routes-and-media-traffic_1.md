---
title: 設定同盟路由與媒體流量
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4542ae02cc72dfbac05dfa982e2fbda7f2924919
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977727"
---
# <a name="configure-federation-routes-and-media-traffic"></a>設定同盟路由與媒體流量

 


同盟是兩個或多個 SIP 網域之間的信任關係，允許個別組織中的使用者在網路界限間進行通訊。 在您遷移至 Lync Server 2013 試生產池之後，您必須從 Microsoft Office 通訊伺服器 2007 R2 Edge 伺服器的同盟路由轉換為 Lync Server 2013 Edge 伺服器的同盟路由。

使用下列程式，將同盟路由及媒體流量路由從您的 Office 通訊伺服器 2007 R2 Edge 伺服器與控制器轉移到 Lync Server 2013 Edge 伺服器（針對單一網站部署）。


> [!IMPORTANT]  
> 變更同盟路由和媒體流量路由時，需要您針對 Lync Server 2013 和 Office 通訊伺服器 2007 R2 Edge 伺服器排程維護時間。 此整個轉換程式也表示在停用期間將無法使用聯盟存取。 您應該將停機時間排程為預期最少的使用者活動。 您也應該為您的最終使用者提供足夠的通知。 針對此中斷進行規劃，並在您的組織中設定適當的預期。




> [!IMPORTANT]  
> 如果您的舊版 Office 通訊伺服器 2007 R2 Edge 伺服器已設定為使用 [存取邊緣服務]、[Web 會議 Edge 服務] 和 [A/V 邊緣] 服務的相同 FQDN，則不支援此區段中的程式將同盟設定轉換為 Lync Server 2013 Edge 伺服器。 如果舊版 Edge 服務設定為使用相同的 FQDN，您必須先將所有使用者從 Office 通訊伺服器 2007 R2 遷移至 Lync Server 2013，然後在啟用同盟之前，先解除 Office 通訊伺服器 2007 R2 Edge 伺服器Lync Server 2013 Edge 伺服器。 如需詳細資訊，請參閱下列主題： 
> <UL>
> <LI>
> <P><A href="move-remaining-users-to-lync-server-2013_1.md">將剩餘使用者移到 Lync Server 2013</A></P>
> <LI>
> <P>"移除伺服器和伺服器角色"<A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></P></LI></UL>




> [!IMPORTANT]  
> 如果您的 XMPP 同盟是透過 Lync Server 2013 Edge 伺服器路由，舊版 Office 通訊伺服器 2007 R2 使用者將無法與 XMPP 聯盟夥伴通訊，除非已將所有使用者移至 Lync Server 2013、XMPP 原則和已設定憑證之後，已在 Lync Server 2013 上設定 XMPP 聯盟合作夥伴，最後更新了 DNS 專案。



若要在新增或移除伺服器角色時成功發佈、啟用或停用拓撲，您應該以 RTCUniversalServerAdmins 和網域系統管理員群組成員的使用者身分登入。 您也可以委派適當的使用者權利和許可權來新增伺服器角色。 如需詳細資訊，請參閱在標準版 server 或 Enterprise Edition server 部署檔中的[Lync Server 2013 委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。 針對其他設定變更，只需要 RTCUniversalServerAdmins 群組中的成員資格。

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>若要從 Lync Server 2013 網站移除舊版同盟關聯

1.  使用 [拓撲建立器] 開啟 [試驗] 泳池拓撲。

2.  在左窗格中，流覽至 [網站] 節點。

3.  以滑鼠右鍵按一下網站，然後按一下 [**編輯屬性**]。

4.  選取左窗格中的 [**同盟路由**]。

5.  在 [網站同盟路由指派] 下，清除 [**啟用 SIP 聯盟**] 旁的核取方塊，以停用**BackCompatSite**的同盟路由。
    
    [![編輯屬性] 對話方塊、[同盟路由](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "編輯屬性] 對話方塊、[同盟] 路由")

6.  按一下 **[確定]** 以關閉 [編輯屬性] 頁面。

7.  從**拓撲**建立器中，選取頂端節點**Lync Server**。

8.  從 [**動作**] 功能表中，按一下 [**發佈拓撲**] 並完成嚮導。

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>將舊版 Edge 伺服器設定為非聯盟邊緣伺服器

1.  從 [**拓撲**建立器] 的 [**動作**] 功能表中，按一下 [**合併 Office 通訊伺服器 2007 R2 拓撲結構**]。

2.  請按 [下一步]**** 繼續。

3.  在 [**指定邊緣設定**] 上，選取目前針對 [同盟] 設定的**邊緣伺服器內部 FQDN** ，然後按一下 [**變更**]。
    
    [![合併 OCS 2007 R2 拓撲]，指定 [邊緣設定]](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "合併 OCS 2007 R2 拓撲，指定邊緣設定")

4.  按一下 **[下一步]** ，接受預設設定，直到您到達 [**指定外部邊緣**] 頁面為止：
    
    ![拓撲建立器指定外部邊緣頁面](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "拓撲建立器指定外部邊緣頁面")

5.  在 [**指定外部邊緣**] 中，清除 [**此 Edge 池用於同盟與公用 IM**連線] 核取方塊。 這將會移除與 BackCompatSite 的同盟關聯。
    

    > [!IMPORTANT]  
    > 這個步驟非常重要。 您必須清除此選項才能移除舊版同盟關聯。



6.  按一下 **[下一步**]，然後接受嚮導剩餘頁面的預設設定。

7.  在 [**摘要**] 中，按一下 **[下一步]** 以開始合併拓撲。

8.  在 [**狀態**] 欄中，確認此值為 [**成功**]，然後按一下 **[完成**] 以關閉嚮導。

9.  從 [**動作**] 功能表中，選取 [**發佈拓撲**]，然後按一下 **[下一步]**。

10. **發佈嚮導**完成後，請按一下 **[完成**] 以關閉嚮導。
    
    [拓撲建立器] ![，其中包含在]合併拓撲建立器之後顯示網站(images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "的")網站
    
    如上圖所示，位於 [**網站同盟路由指派**] 下的**SIP 同盟**設定為 [**已停用**]。

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a>在 Lync Server 2013 Edge 伺服器上設定憑證

1.  從舊版 Office 通訊伺服器 2007 R2 Edge 伺服器匯出外部存取 Proxy 證書與私密金鑰。

2.  在 Lync Server 2013 Edge 伺服器上，從上一個步驟匯入 [存取 Proxy 外部憑證]。

3.  將存取 Proxy 外部憑證指派給 Edge 伺服器的 Lync Server 2013 外部介面。

4.  Lync Server 2013 Edge 伺服器的內部介面憑證不應變更。

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a>若要將 Office 通訊伺服器 2007 R2 同盟路由變更為使用 Lync Server 2013 Edge 伺服器

1.  在 Office 通訊伺服器 2007 R2 標準版伺服器或前端伺服器上，開啟 Office 通訊伺服器 2007 R2 管理工具。

2.  在左窗格中，展開上方節點，然後以滑鼠右鍵按一下 [**林**] 節點。 選取 [**屬性**]，然後按一下 [**全域屬性**]。

3.  按一下 [**聯盟**] 索引標籤。

4.  選取核取方塊以啟用同盟與公用 IM 連線。

5.  輸入 Lync Server 2013 Edge 伺服器的 FQDN，然後按一下 **[確定]**。
    
    ![Ocs 全域屬性、[同盟]]索引標籤(images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS 全域屬性、[同盟]")索引標籤

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>若要開啟 Lync Server 2013 Edge 伺服器同盟

1.  從拓撲建立器，在左窗格中，流覽至 [Lync Server 2013 **Edge 池**] 節點。

2.  展開節點，以滑鼠右鍵按一下列出的邊緣伺服器，然後按一下 [**編輯屬性**]。
    

    > [!NOTE]  
    > 只有單一邊緣池才能啟用同盟。 如果您有多個邊緣池，請選取一個，以做為聯盟邊界池。



3.  在 [**一般**] 頁面上，選取 [**針對此 Edge 池啟用同盟（埠5061）** ] 核取方塊。
    
    ![編輯屬性、一般、啟用邊緣同盟](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "編輯屬性、一般、啟用邊緣同盟")

4.  按一下 **[確定]** 以關閉 [編輯屬性] 頁面。

5.  接下來，流覽至 [網站] 節點。

6.  以滑鼠右鍵按一下網站，然後按一下 [**編輯屬性**]。

7.  在左窗格中，按一下 [**同盟路由**]。

8.  在 [**網站同盟路由指派**] 底下，選取 [**啟用 SIP 同盟**]，然後從清單中選取 [Lync server 2013 Edge 伺服器]。

9.  按一下 **[確定]** 以關閉 [**編輯屬性**] 頁面。
    
    ![編輯屬性、一般、關聯邊緣池](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "編輯屬性、一般、關聯邊緣池")
    
    針對多網站部署，請在每個網站完成此程式。

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>設定 Lync Server 2013 Edge 伺服器出站媒體路徑

1.  從**拓撲**建立器，流覽至**標準版前端伺服器**或**企業版前端池**下方的 Lync Server 2013 池。

2.  以滑鼠右鍵按一下該池子，然後按一下 [**編輯屬性**]。

3.  在 [**關聯**性] 區段中，選取 [**關聯邊緣池（適用于媒體元件）** ] 核取方塊。

4.  從下拉式方塊中，選取 [Lync Server 2013 Edge 伺服器]。
    
    [![編輯屬性] 對話方塊、[關聯邊緣池]] [(images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "編輯屬性] 對話方塊、[關聯邊緣] 池")

5.  按一下 **[確定]** 以關閉 [**編輯屬性**] 頁面。

## <a name="to-publish-edge-server-configuration-changes"></a>發佈 Edge 伺服器設定變更

1.  從**拓撲**建立器中，選取頂端節點**Lync Server**。

2.  從 [**動作**] 功能表中，選取 [**發佈拓撲**] 並完成嚮導。

3.  等到對部署中的所有池進行 Active Directory 複製。
    

    > [!NOTE]  
    > 您可能會看到下列訊息：<BR><STRONG>警告：拓朴包含一個以上的同盟邊緣伺服器。在遷移到較新版產品的過程中，可能會發生這種情況。在這種情況下，只有一台邊緣伺服器會主動用於同盟。確認外部 DNS SRV 記錄指向正確的邊緣伺服器。如果您想要將多個同盟邊緣伺服器部署成同時作用（也就是不是遷移案例），請確認所有聯盟夥伴都使用 Office 通訊伺服器 2007 R2 或 Lync Server。確認外部 DNS SRV 記錄列出所有啟用同盟的 Edge 伺服器。</STRONG><BR>此為預期警告，且可以放心地忽略。



## <a name="to-verify-federation-and-remote-access-for-external-users"></a>驗證外部使用者的同盟與遠端存取權

1.  從 Lync Server 2013 前端伺服器，開啟 Lync Server 管理命令介面。

2.  若要驗證同盟和遠端存取的狀態，請從命令列輸入下列內容：
    
        Get-CsAccessEdgeConfiguration

3.  若要啟用同盟和遠端存取，請從命令列輸入下列內容：
    
        Set-CsAccessEdgeConfiguration
    
    如需這些 Cmdlet 的詳細資訊，請參閱下列主題： [CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg398574\(v=ocs.15\))及[設定 CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg413017\(v=ocs.15\))。

4.  等到複製完成之後，再將 Lync Server 2013 Edge 伺服器連線，然後測試同盟與外部存取。

## <a name="to-configure-lync-server-2013-edge-server"></a>設定 Lync Server 2013 Edge 伺服器

1.  將所有 Lync Server 2013 Edge 伺服器連線。

2.  更新外部防火牆路由規則或硬體負載平衡器設定，以傳送 SIP 流量（通常是埠443）和同盟（通常是埠5061）至 Lync Server 2013 Edge 伺服器，而不是舊版 Edge 伺服器。
    

    > [!NOTE]  
    > 如果您沒有硬體負載平衡器，您需要更新同盟的 DNS A 記錄，以解析新的 Lync Server Access Edge 伺服器。 若要以最小的中斷來完成此作業，請減少外部 Lync Server 存取邊緣 FQDN 的 TTL 值，以便將 DNS 更新為指向新的 Lync Server 存取邊緣伺服器、同盟和遠端存取將會很快更新。



3.  接下來，從每個 Edge 伺服器電腦停止**Lync Server 存取邊緣**。

4.  從每個舊版 Edge 伺服器電腦，從 [**管理工具**] 開啟 [**服務**] 小工具。

5.  在 [服務] 清單中，尋找 [ **Office 通訊伺服器存取邊緣**]。

6.  以滑鼠右鍵按一下服務名稱，然後選取 [**停止**] 停止服務。

7.  將啟動類型設定為 [**停用**]。

8.  按一下 **[確定**] 以關閉 [**屬性**] 視窗。

## <a name="to-test-connectivity-of-external-users-and-external-access"></a>測試外部使用者與外部存取的連線能力

  - 至少有一個聯盟網域的使用者，也就是 Lync Server 2013 上的內部使用者，以及 Office 通訊伺服器 2007 R2 上的使用者。 測試立即訊息（IM）、目前狀態、音訊/視頻（A/V）與桌面共用。

  - 貴組織支援的每個公用 IM 服務提供者的使用者（以及已完成哪些預配）與 Lync Server 2013 上的使用者通訊，以及 Office 通訊伺服器 2007 R2 上的使用者。

  - 確認匿名使用者可以加入會議。

  - 在 Office 通訊伺服器 2007 R2 上使用遠端使用者存取（從內部網路外部（不含 VPN）登入 Office 通訊伺服器 2007 R2 的使用者，與 Lync Server 2013 上的使用者，以及 Office 通訊伺服器 2007 R2 上的使用者。 測試 IM、目前狀態、A/V 與桌面共用。

  - 在 Lync Server 2013 上使用遠端使用者存取（從內部網路外部2013（不含 VPN）與使用者在 Lync server 2013 上以及 Office 通訊伺服器 2007 R2 上的使用者所託管的使用者。 測試 IM、目前狀態、A/V 與桌面共用。

