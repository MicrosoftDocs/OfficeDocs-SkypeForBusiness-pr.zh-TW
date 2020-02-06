---
title: 設定同盟路由與媒體流量
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 同盟是兩個或多個 SIP 網域之間的信任關係，允許個別組織中的使用者在網路界限間進行通訊。 在您遷移到您的試用版池之後，您必須從舊版 Edge 伺服器的同盟路由轉換到商務用 Skype Server 2019 Edge 伺服器的同盟路由。
ms.openlocfilehash: 71417307fd46c2c29535cea3a52f0286ad6dc951
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813811"
---
# <a name="configure-federation-routes-and-media-traffic"></a>設定同盟路由與媒體流量

同盟是兩個或多個 SIP 網域之間的信任關係，允許個別組織中的使用者在網路界限間進行通訊。 在您遷移到您的試驗池之後，您必須從先前版本的邊緣伺服器的同盟路由轉移到商務用 Skype Server 2019 Edge 伺服器的同盟路由。
  
您可以使用下列程式，將同盟路由及媒體流量路由從舊版的 Edge 伺服器與控制器轉換成商務用 Skype Server 2019 Edge 伺服器（針對單一網站部署）。
  
> [!IMPORTANT]
> 變更同盟路由和媒體流量路由時，需要您針對商務用 Skype Server 2019 和舊版 Edge 伺服器排程維護時間。 此整個轉換程式也表示在停用期間將無法使用聯盟存取。 您應該將停機時間排程為預期最少的使用者活動。 您也應該為您的最終使用者提供足夠的通知。 針對此中斷進行規劃，並在您的組織中設定適當的預期。 
  
> [!IMPORTANT]
> 如果您的舊版 Edge 伺服器已設定為使用相同的 FQDN 來存取邊緣服務、網路會議邊緣服務以及 A/V 邊緣服務，則不支援本節中的程式。 如果舊版 Edge 服務設定為使用相同的 FQDN，您必須先遷移所有的使用者，然後在商務用 Skype Server 2019 Edge 伺服器上啟用同盟之後，再解除舊版 Edge 伺服器。 
  
> [!IMPORTANT]
> 如果您的 XMPP 同盟是透過商務用 Skype Server 2019 Edge 伺服器路由，前一版的使用者將無法與 XMPP 聯盟合作夥伴通訊，除非已將所有使用者移至商務用 Skype Server 2019、XMPP 原則以及已設定憑證之後，已在商務用 Skype Server 2019 上設定 XMPP 聯盟合作夥伴，最後再更新 DNS 專案。 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a>若要從商務用 Skype Server 2019 網站移除舊版同盟關聯

1. 在商務用 Skype Server 2019 前端伺服器上，在 [拓撲產生器] 中開啟現有的拓撲。 
    
2. 在左窗格中，流覽至位於 [**商務用 Skype] 伺服器**正下方的 [網站] 節點。
    
3. 以滑鼠右鍵按一下網站，然後按一下 [**編輯屬性**]。
    
4. 在左窗格中，選取 [**同盟路由**]。 
    
5. 在 [**網站同盟路由指派**] 下，清除 [**啟用 SIP 同盟**] 核取方塊，以停用同盟路由與舊版環境。 
  
6. 按一下 **[確定]** 以關閉 [編輯屬性] 頁面。 
    
7. 從 [**拓撲**建立器] 中，選取 [頂層節點**商務用 Skype Server**]。
    
8. 從 [**動作**] 功能表中，按一下 [**發佈拓撲**]。
    
9. 按一下 **[下一步**] 完成發佈程式，然後在發佈程式完成時按一下 **[完成]** 。 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>將舊版 Edge 伺服器設定為非聯盟邊緣伺服器

1. 在左窗格中，流覽至 [舊版安裝] 節點，然後流覽至 [**邊緣池**] 節點。 
    
2. 以滑鼠右鍵按一下邊緣伺服器，然後按一下 [**編輯屬性**]。
    
3. 在左窗格中選取 **[一般**]。 
    
4. 清除 [**針對此 Edge 池啟用同盟（埠5061）** ] 核取方塊，然後選取 **[確定]** 以關閉頁面。 
  
5. 從 [**動作**] 功能表中，選取 [**發佈拓撲**]，然後按一下 **[下一步]**。
    
6. **發佈嚮導**完成後，請按一下 **[完成**] 以關閉嚮導。 
    
7. 確認 [拓撲建立器] 中已停用舊版 Edge 伺服器的同盟。
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a>在舊版 Edge 伺服器上設定憑證

1. 從舊版 Edge 伺服器匯出外部存取 Proxy 證書與私密金鑰。 
    
2. 在商務用 Skype Server 2019 Edge 伺服器上，然後匯入上一個步驟的 [存取 Proxy 外部憑證]。
    
3. 將存取 Proxy 外部憑證指派給 Edge 伺服器的商務用 Skype Server 2019 外部介面。
    
4. 商務用 Skype Server 2019 Edge 伺服器的內部介面憑證應該從信任的 CA 要求並加以指派。 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a>若要將先前版本的同盟路由變更為使用商務用 Skype Server 2019 Edge 伺服器

1. 從拓撲建立器，在左窗格中，流覽至**商務用 Skype Server 2019**節點，然後移至 [**邊緣池**] 節點。 
    
2. 以滑鼠右鍵按一下邊緣伺服器，然後按一下 [**編輯屬性**]。
    
3. 在左窗格中選取 **[一般**]。 
    
4. 選取 [針對**此 Edge 池啟用同盟（埠5061）**] 的核取方塊，然後按一下 **[確定]** 以關閉頁面。 
  
5. 從 [**動作**] 功能表中，選取 [**發佈拓撲**]，然後按一下 **[下一步]**。
    
6. **發佈嚮導**完成後，請按一下 **[完成**] 以關閉嚮導。 
    
7. 確認 **[同盟（埠5061）** **] 已設定為**[拓撲建立器]。
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a>更新商務用 Skype Server 2019 Edge 伺服器同盟下一個躍點

1. 從拓撲建立器，在左窗格中，流覽至**商務用 Skype Server 2019**節點，然後移至 [**邊緣池**] 節點。 
    
2. 展開節點，以滑鼠右鍵按一下列出的邊緣伺服器，然後按一下 [**編輯屬性**]。 
    
3. 在 [**一般**] 頁面上的 **[下一個躍點選取範圍]** 底下，從下拉式清單中選取 [商務用 Skype Server 2019] 池。
  
4. 按一下 **[確定]** 以關閉 [編輯屬性] 頁面。 
    
5. 從 [**拓撲**建立器] 中，選取 [頂層節點**商務用 Skype Server**]。 
    
6. 從 [**動作**] 功能表中，按一下 [**發佈拓撲**] 並完成嚮導。 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a>若要設定商務用 Skype Server 2019 Edge 伺服器輸出媒體路徑

1. 從 [拓撲建立器]，在左窗格中，流覽至 [**商務用 Skype Server 2019** ] 節點，然後移至 [**標準版] 前端伺服器**或 [**企業版] 前端池**的 [池]。
    
2. 以滑鼠右鍵按一下該池子，然後按一下 [**編輯屬性**]。
    
3. 在 [**關聯**性] 區段中，選取 [**關聯邊緣池（適用于媒體元件）** ] 核取方塊。 
  
4. 從下拉式方塊中，選取 [商務用 Skype Server 2019 Edge 伺服器]。
    
5. 按一下 **[確定]** 以關閉 [**編輯屬性**] 頁面。 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a>開啟商務用 Skype Server 2019 Edge 伺服器同盟

1. 從拓撲建立器，在左窗格中，流覽至**商務用 Skype Server 2019**節點，然後移至 [**邊緣池**] 節點。 
    
2. 展開節點，以滑鼠右鍵按一下列出的邊緣伺服器，然後按一下 [**編輯屬性**]。 
    
    > [!NOTE]
    > 只有單一邊緣池才能啟用同盟。 如果您有多個邊緣池，請選取一個，以做為聯盟邊界池。 
  
3. 在 [**一般**] 頁面上，確認已選取 [**針對此 Edge 池啟用同盟（埠5061）** ] 核取方塊。 
  
4. 按一下 **[確定]** 以關閉 [編輯屬性] 頁面。 
    
5. 流覽至 [網站] 節點。 
    
6. 以滑鼠右鍵按一下網站，然後按一下 [**編輯屬性**]。
    
7. 在左窗格中，按一下 [**同盟路由**]。
    
8. 在 [**網站同盟路由指派**] 底下，選取 [**啟用 SIP 同盟**]，然後從清單中選取 [商務用 Skype server 2019 Edge 伺服器]。 
  
9. 按一下 **[確定]** 以關閉 [**編輯屬性**] 頁面。 
    
     針對多網站部署，請在每個網站完成此程式。 
    
## <a name="to-publish-edge-server-configuration-changes"></a>發佈 Edge 伺服器設定變更

1. 從 [**拓撲**建立器] 中，選取 [頂層節點**商務用 Skype Server**]。 
    
2. 從 [**動作**] 功能表中，選取 [**發佈拓撲**] 並完成嚮導。 
    
3. 等到對部署中的所有池進行 Active Directory 複製。
    
    > [!NOTE]
    > 您可能會看到下列訊息：**警告：拓撲包含一個以上的同盟邊緣伺服器。在遷移到較新版產品的過程中，可能會發生這種情況。在這種情況下，只有一台邊緣伺服器會主動用於同盟。確認外部 DNS SRV 記錄指向正確的邊緣伺服器。如果您想要將多個同盟邊緣伺服器部署成同時作用（也就是不是遷移案例），請確認所有聯盟夥伴都使用商務用 Skype 伺服器。確認外部 DNS SRV 記錄列出所有啟用同盟的 Edge 伺服器。** 此為預期警告，且可以放心地忽略。 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a>若要設定商務用 Skype Server 2019 Edge 伺服器

1. 將所有商務用 Skype Server 2019 Edge 伺服器連線。 
    
2. 更新外部防火牆路由規則或硬體負載平衡器設定，以將外部存取（通常是埠443）和同盟（通常是埠5061）的 SIP 流量傳送到商務用 Skype Server 2019 Edge 伺服器，而不是舊版 Edge 伺服器。
    
    > [!NOTE]
    > 如果您沒有硬體負載平衡器，您需要更新同盟的 DNS A 記錄，以解析為新的商務用 Skype Server 存取邊緣伺服器。 若要以最小的中斷來完成這項作業，請減少外部商務用 Skype Server 存取邊緣 FQDN 的 TLL 值，讓 DNS 更新為指向新的商務用 Skype Server 存取邊緣、同盟和遠端存取將會很快更新。 
  
3. 停止每個 Edge 伺服器電腦上的**商務用 Skype Server 存取邊緣**。 
    
4. 從每個舊版 Edge 伺服器電腦，從 [**管理工具**] 開啟 [**服務**] 小工具。
    
5. 在 [服務] 清單中，尋找**商務用 Skype Server 存取邊緣**。
    
6. 以滑鼠右鍵按一下服務名稱，然後選取 [**停止**] 停止服務。 
    
7. 將啟動類型設定為 [**停用**]。 
    
8. 按一下 **[確定**] 以關閉 [**屬性**] 視窗。 
    

