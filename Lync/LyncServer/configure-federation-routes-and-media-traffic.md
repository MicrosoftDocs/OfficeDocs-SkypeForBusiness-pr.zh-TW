---
title: 設定同盟路由與媒體流量
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
ms.openlocfilehash: 9cd9cf1c7c61261e4e1a6974498f9f9dff980169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-routes-and-media-traffic"></a>設定同盟路由與媒體流量

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-15_

同盟是兩個或多個 SIP 網域之間的信任關係，允許個別組織中的使用者在網路界限間進行通訊。 在您遷移至 Lync Server 2013 試生產池之後，您必須從 Lync Server 2010 Edge 伺服器的同盟路由轉移到 Lync Server 2013 Edge 伺服器的同盟路由。

您可以使用下列程式，將同盟路由及媒體流量路由從 Lync Server 2010 Edge 伺服器與控制器轉換為 Lync Server 2013 Edge 伺服器（針對單一網站部署）。

<div>


> [!IMPORTANT]  
> 變更同盟路由和媒體流量路由時，需要您針對 Lync Server 2013 和 Lync Server 2010 Edge 伺服器排程維護時間。 此整個轉換程式也表示在停用期間將無法使用聯盟存取。 您應該將停機時間排程為預期最少的使用者活動。 您也應該為您的最終使用者提供足夠的通知。 針對此中斷進行規劃，並在您的組織中設定適當的預期。



</div>

<div>


> [!IMPORTANT]  
> 如果您的舊版 Lync Server 2010 Edge 伺服器已設定為使用相同的 FQDN 來存取邊緣服務、網路會議邊緣服務以及 A/V 邊緣服務，則不支援本節中的程式。 如果舊版 Edge 服務設定為使用相同的 FQDN，您必須先將所有使用者從 Lync Server 2010 遷移至 Lync Server 2013，然後在 Lync Server 2013 Edge 伺服器上啟用同盟之前，先解除 Lync Server 2010 Edge 伺服器。



</div>

<div>


> [!IMPORTANT]  
> 如果您的 XMPP 同盟是透過 Lync Server 2013 Edge 伺服器路由，舊版 Lync Server 2010 使用者將無法與 XMPP 聯盟夥伴通訊，除非已將所有使用者移至 Lync Server 2013、XMPP 原則與憑證已設定，已在 Lync Server 2013 上設定 XMPP 聯盟合作夥伴，最後更新了 DNS 專案。



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>若要從 Lync Server 2013 網站移除舊版同盟關聯

1.  在 Lync Server 2013 前端伺服器上，在 [拓撲產生器] 中開啟現有的拓撲。

2.  在左窗格中，流覽至 [ **Lync Server**] 正下方的 [網站] 節點。

3.  以滑鼠右鍵按一下網站，然後按一下 [**編輯屬性**]。

4.  在左窗格中，選取 [**同盟路由**]。

5.  在 [**網站同盟路由指派**] 下，清除 [**啟用 SIP 同盟**] 核取方塊，以停用來自舊版 Lync Server 2010 環境的同盟路由。
    
    ![[編輯內容] 對話方塊，[同盟路由] 頁面](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "[編輯內容] 對話方塊，[同盟路由] 頁面")

6.  按一下 **[確定]** 以關閉 [編輯屬性] 頁面。

7.  從**拓撲**建立器中，選取頂端節點**Lync Server**。

8.  從 [**動作**] 功能表中，按一下 [**發佈拓撲**]。

9.  按一下 **[下一步**] 完成發佈程式，然後在發佈程式完成時按一下 **[完成]** 。

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>將舊版 Edge 伺服器設定為非聯盟邊緣伺服器

1.  在左窗格中，流覽至**Lync Server 2010**節點，然後移至 [**邊緣池**] 節點。

2.  以滑鼠右鍵按一下邊緣伺服器，然後按一下 [**編輯屬性**]。

3.  在左窗格中選取 **[一般**]。

4.  清除 [**針對此 Edge 池啟用同盟（埠5061）** ] 核取方塊專案，然後選取 **[確定]** 以關閉頁面。
    
    ![編輯內容，一般，清除啟用同盟](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "編輯內容，一般，清除啟用同盟")

5.  從 [**動作**] 功能表中，選取 [**發佈拓撲**]，然後按一下 **[下一步]**。

6.  **發佈嚮導**完成後，請按一下 **[完成**] 以關閉嚮導。

7.  驗證舊版 Edge 伺服器的同盟已停用。
    
    ![拓撲產生器，Edge 集區，已停用同盟](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "拓撲產生器，Edge 集區，已停用同盟")

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a>在 Lync Server 2010 Edge 伺服器上設定憑證

1.  從舊版 Lync Server 2010 Edge 伺服器匯出外部存取 Proxy 證書與私密金鑰。

2.  在 Lync Server 2013 Edge 伺服器上，從上一個步驟匯入 [存取 Proxy 外部憑證]。

3.  將存取 Proxy 外部憑證指派給 Edge 伺服器的 Lync Server 2013 外部介面。

4.  必須從信任的 CA 要求並指派 Lync Server 2013 Edge 伺服器的內部介面憑證。

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a>若要將 Lync Server 2010 同盟路由變更為使用 Lync Server 2013 Edge 伺服器

1.  從拓撲建立器，在左窗格中，流覽至**Lync Server 2013**節點，然後流覽至 [**邊緣池**] 節點。

2.  以滑鼠右鍵按一下邊緣伺服器，然後按一下 [**編輯屬性**]。

3.  在左窗格中選取 **[一般**]。

4.  選取 [針對**此 Edge 池啟用同盟的核取方塊專案（埠5061）** ]，然後按一下 **[確定]** 以關閉頁面。
    
    ![[編輯內容] 對話方塊，[一般] 頁面](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "[編輯內容] 對話方塊，[一般] 頁面")

5.  從 [**動作**] 功能表中，選取 [**發佈拓撲**]，然後按一下 **[下一步]**。

6.  **發佈嚮導**完成後，請按一下 **[完成**] 以關閉嚮導。

7.  驗證**同盟（埠5061）** 已設定為 [**啟用**]。
    
    ![拓撲產生器，Edge 集區，已啟用同盟](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "拓撲產生器，Edge 集區，已啟用同盟")

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a>更新 Lync Server 2013 Edge 伺服器同盟下一個躍點

1.  從拓撲建立器，在左窗格中，流覽至**Lync Server 2013**節點，然後流覽至 [**邊緣池**] 節點。

2.  展開節點，以滑鼠右鍵按一下列出的邊緣伺服器，然後按一下 [**編輯屬性**]。

3.  在 [**一般**] 頁面上的 **[下一個躍點選取範圍]** 底下，從下拉式清單中選取 [Lync Server 2013] 池。
    
    ![[編輯內容] 對話方塊，[下一個躍點] 頁面](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "[編輯內容] 對話方塊，[下一個躍點] 頁面")

4.  按一下 **[確定]** 以關閉 [編輯屬性] 頁面。

5.  從**拓撲**建立器中，選取頂端節點**Lync Server** 。

6.  從 [**動作**] 功能表中，按一下 [**發佈拓撲**] 並完成嚮導。

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>設定 Lync Server 2013 Edge 伺服器出站媒體路徑

1.  從 [拓撲建立器] 的左窗格中，流覽至 [ **Lync Server 2013** ] 節點，然後移至 [**標準版] 前端伺服器**或 [**企業版] 前端池**的 [池]。

2.  以滑鼠右鍵按一下該池子，然後按一下 [**編輯屬性**]。

3.  在 [**關聯**性] 區段中，選取 [**關聯邊緣池（適用于媒體元件）** ] 核取方塊。
    
    ![編輯內容，一般，關聯 Edge 集區](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "編輯內容，一般，關聯 Edge 集區")

4.  從下拉式方塊中，選取 [Lync Server 2013 Edge 伺服器]。

5.  按一下 **[確定]** 以關閉 [**編輯屬性**] 頁面。

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>若要開啟 Lync Server 2013 Edge 伺服器同盟

1.  從拓撲建立器，在左窗格中，流覽至**Lync Server 2013**節點，然後流覽至 [**邊緣池**] 節點。

2.  展開節點，以滑鼠右鍵按一下列出的邊緣伺服器，然後按一下 [**編輯屬性**]。
    
    <div>
    

    > [!NOTE]  
    > 只有單一邊緣池才能啟用同盟。 如果您有多個邊緣池，請選取一個，以做為聯盟邊界池。

    
    </div>

3.  在 [**一般**] 頁面上，確認已核取 [**啟用此 Edge 池的同盟（埠5061）** ] 設定。
    
    ![[編輯內容] 對話方塊，[一般] 頁面](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "[編輯內容] 對話方塊，[一般] 頁面")

4.  按一下 **[確定]** 以關閉 [編輯屬性] 頁面。

5.  接下來，流覽至 [網站] 節點。

6.  以滑鼠右鍵按一下網站，然後按一下 [**編輯屬性**]。

7.  在左窗格中，按一下 [**同盟路由**]。

8.  在 [**網站同盟路由指派**] 底下，選取 [**啟用 SIP 同盟**]，然後從清單中選取 [Lync server 2013 Edge 伺服器]。
    
    ![編輯內容，[同盟路由] 頁面](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "編輯內容，[同盟路由] 頁面")

9.  按一下 **[確定]** 以關閉 [**編輯屬性**] 頁面。
    
    針對多網站部署，請在每個網站完成此程式。

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a>發佈 Edge 伺服器設定變更

1.  從**拓撲**建立器中，選取頂端節點**Lync Server** 。

2.  從 [**動作**] 功能表中，選取 [**發佈拓撲**] 並完成嚮導。

3.  等到對部署中的所有池進行 Active Directory 複製。
    
    <div>
    

    > [!NOTE]  
    > 您可能會看到下列訊息：<BR><STRONG>警告：拓朴包含一個以上的同盟邊緣伺服器。在遷移到較新版產品的過程中，可能會發生這種情況。在這種情況下，只有一台邊緣伺服器會主動用於同盟。確認外部 DNS SRV 記錄指向正確的邊緣伺服器。如果您想要將多個同盟邊緣伺服器部署成同時作用（也就是不是遷移案例），請確認所有聯盟夥伴都使用 Lync Server。確認外部 DNS SRV 記錄列出所有啟用同盟的 Edge 伺服器。</STRONG><BR>此為預期警告，且可以放心地忽略。

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a>設定 Lync Server 2013 Edge 伺服器

1.  將所有 Lync Server 2013 Edge 伺服器連線。

2.  更新外部防火牆路由規則或硬體負載平衡器設定，以傳送 SIP 流量（通常是埠443）和同盟（通常是埠5061）至 Lync Server 2013 Edge 伺服器，而不是舊版 Edge 伺服器。
    
    <div>
    

    > [!NOTE]  
    > 如果您沒有硬體負載平衡器，您需要更新同盟的 DNS A 記錄，以解析為新的 Lync Server 存取邊緣伺服器。 若要以最小的中斷來完成此作業，請減少外部 Lync Server 存取邊緣 FQDN 的 TLL 值，讓 DNS 更新為指向新的 Lync Server 存取邊緣、同盟和遠端存取將會很快更新。

    
    </div>

3.  接下來，從每個 Edge 伺服器電腦停止**Lync Server 存取邊緣**。

4.  從每個舊版 Edge 伺服器電腦，從 [**管理工具**] 開啟 [**服務**] 小工具。

5.  在 [服務] 清單中，尋找 [ **Lync Server 存取權] 邊緣**。

6.  以滑鼠右鍵按一下服務名稱，然後選取 [**停止**] 停止服務。

7.  將啟動類型設定為 [**停用**]。

8.  按一下 **[確定**] 以關閉 [**屬性**] 視窗。

</div>

</div>

<span> </span>

</div>

</div>

</div>

