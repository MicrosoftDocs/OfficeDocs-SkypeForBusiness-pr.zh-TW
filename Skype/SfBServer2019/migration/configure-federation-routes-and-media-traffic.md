---
title: 設定同盟路由與媒體流量
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 同盟是兩個或兩個以上 SIP 網域間的信任關係，其可允許不同組織中的使用者跨越網路界限進行通訊。 遷移至試驗集區之後，您必須從舊版 Edge Server 的同盟路由轉換為商務用 Skype Server 2019 Edge Server 的同盟路由。
ms.openlocfilehash: 2fafe991b8d09a477d084bdf2081d240e4830589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754033"
---
# <a name="configure-federation-routes-and-media-traffic"></a>設定同盟路由與媒體流量

同盟是兩個或兩個以上 SIP 網域間的信任關係，其可允許不同組織中的使用者跨越網路界限進行通訊。 遷移至試驗集區之後，您必須從舊版之 Edge Server 的同盟路由轉換為商務用 Skype Server 2019 Edge Server 的同盟路由。
  
請使用下列程式，將舊版之 Edge Server 和 Director 的同盟路由與媒體流量路由轉換為商務用 Skype Server 2019 Edge Server，以進行單一網站部署。
  
> [!IMPORTANT]
> 變更同盟路由與媒體流量路由需要您為商務用 Skype Server 2019 和舊版 Edge server 排程維護停機時間。 這整個轉換過程同時也意味著，在運行中斷期間無法使用同盟存取。 您應該將停機時間排在您預期使用者活動最少的時間。 您也應該要提供足夠的通知給您的使用者。 請視情況規劃此運行中斷，並且在組織內設定適當的期望。 
  
> [!IMPORTANT]
> 如果舊版 Edge Server 設定為使用「Access Edge service」、「Web 會議 Edge service」和「A/V Edge service」的相同 FQDN，則不支援本節中的程式。 如果舊版 Edge service 設定為使用相同的 FQDN，您必須先遷移所有的使用者，然後在啟用商務用 Skype Server 2019 Edge Server 上的同盟之前，解除舊版 Edge Server 的授權。 
  
> [!IMPORTANT]
> 如果您的 XMPP 同盟是透過商務用 Skype Server 2019 Edge Server 路由傳送，舊版的使用者將無法與 XMPP 同盟協力廠商通訊，除非所有使用者都已移至商務用 Skype Server 2019、已設定 XMPP 原則和憑證，但已在商務用 Skype Server 2019 上設定 XMPP 同盟協力廠商。和，最後，已更新 DNS 專案。 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a>從商務用 Skype Server 2019 網站移除舊版同盟關聯

1. 在商務用 Skype Server 2019 前端伺服器上，在拓撲產生器中開啟現有的拓撲。 
    
2. 在左窗格中，流覽至網站節點，該節點直接位於商務用**Skype Server**。
    
3. 以滑鼠右鍵按一下站台，然後按一下 [編輯屬性]****。
    
4. 在左窗格中，選取 [**同盟路由**]。 
    
5. 在 [**網站同盟路由指派**] 底下，清除 [**啟用 SIP 同盟**] 核取方塊，以停用透過舊版環境的同盟路由。 
  
6. 按一下 [確定]****，以關閉 [編輯屬性] 頁面。 
    
7. 從 [**拓撲**產生器] 中，選取上方節點的**商務用 Skype 伺服器**。
    
8. 從 [**動作**] 功能表中，按一下 [**發行拓撲**]。
    
9. 按 **[下一步]** 完成發佈程式，然後在發佈程式完成時按一下 **[完成]** 。 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>將舊版 Edge Server 設定成非同盟 Edge Server

1. 在左窗格中，流覽至 [舊版安裝] 節點，然後流覽至 [ **Edge**集區] 節點。 
    
2. 以滑鼠右鍵按一下 Edge server，然後按一下 [**編輯屬性**]。
    
3. 在左窗格中選取 **[一般**]。 
    
4. 清除 [**啟用此 Edge 集區的同盟（埠5061）** ] 核取方塊，然後選取 **[確定]** 以關閉頁面。 
  
5. 從 [**動作**] 功能表中，選取 [**發行拓撲**]，然後按 **[下一步]**。
    
6. 當 [發行精靈]**** 完成之後，按一下 [完成]****，以關閉精靈。 
    
7. 確認已在拓撲產生器中停用舊版 Edge server 的同盟。
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a>在舊版 Edge Server 上設定憑證

1. 從舊版 Edge Server 匯出外部存取 Proxy 憑證與私密金鑰。 
    
2. 在商務用 Skype Server 2019 Edge Server 上，然後匯入上一個步驟的 Access Proxy 外部憑證。
    
3. 將 Access Proxy 外部憑證指派給 Edge Server 的商務用 Skype Server 2019 外部介面。
    
4. 商務用 Skype Server 2019 Edge Server 的內部介面憑證應從信任的 CA 要求並被指派。 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a>若要變更先前版本的同盟路由，以使用商務用 Skype Server 2019 Edge Server

1. 在 [拓撲產生器] 的左窗格中，流覽至 [**商務用 Skype 伺服器 2019** ] 節點，然後流覽至 [ **Edge**集區] 節點。 
    
2. 以滑鼠右鍵按一下 Edge server，然後按一下 [**編輯屬性**]。
    
3. 在左窗格中選取 **[一般**]。 
    
4. 選取 [**啟用此 Edge 集區的同盟（埠5061）**] 核取方塊，然後按一下 **[確定]** 以關閉頁面。 
  
5. 從 [**動作**] 功能表中，選取 [**發行拓撲**]，然後按 **[下一步]**。
    
6. 當 [發行精靈]**** 完成之後，按一下 [完成]****，以關閉精靈。 
    
7. 確認已在拓撲產生器中將**同盟（埠5061）** 設為 [**已啟用**]。
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a>更新商務用 Skype Server 2019 Edge Server 同盟的下一個躍點

1. 在 [拓撲產生器] 的左窗格中，流覽至 [**商務用 Skype 伺服器 2019** ] 節點，然後流覽至 [ **Edge**集區] 節點。 
    
2. 展開節點，再以滑鼠右鍵按一下所列出的 Edge Server，然後按一下 [編輯屬性]****。 
    
3. 在 [**一般**] 頁面的 **[下一個躍點選取範圍]** 下，從下拉式清單中選取 [商務用 Skype 伺服器2019集區]。
  
4. 按一下 [確定]****，以關閉 [編輯屬性] 頁面。 
    
5. 從 [**拓撲**產生器] 中，選取上方節點的**商務用 Skype 伺服器**。 
    
6. 從 [**動作**] 功能表中，按一下 [**發行拓撲**]，然後完成嚮導。 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a>設定商務用 Skype Server 2019 Edge Server 輸出媒體路徑

1. 在 [拓撲產生器] 的左窗格中，流覽至 [**商務用 Skype 伺服器 2019** ] 節點，然後流覽至 [ **Standard edition 前端伺服器**] 或 [ **Enterprise edition 前端**集區] 底下的集區。
    
2. 以滑鼠右鍵按一下集區，然後按一下 [編輯屬性]****。
    
3. 選取 [關聯]**** 區段底下的 [關聯 Edge 集區 (適用於媒體元件)]**** 核取方塊。 
  
4. 從下拉式清單方塊中，選取商務用 Skype Server 2019 Edge Server。
    
5. 按一下 [確定]**** 關閉 [編輯內容]**** 頁面。 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a>開啟商務用 Skype Server 2019 Edge Server federation

1. 在 [拓撲產生器] 的左窗格中，流覽至 [**商務用 Skype 伺服器 2019** ] 節點，然後流覽至 [ **Edge**集區] 節點。 
    
2. 展開節點，再以滑鼠右鍵按一下所列出的 Edge Server，然後按一下 [編輯屬性]****。 
    
    > [!NOTE]
    > 只可對單一 Edge 集區啟用同盟。 如果您有多個 Edge 集區，請選取其中一個做為同盟 Edge 集區。 
  
3. 在 [**一般**] 頁面上，確認已選取 [**啟用此 Edge 集區的同盟（埠5061）** ] 核取方塊。 
  
4. 按一下 [確定]****，以關閉 [編輯屬性] 頁面。 
    
5. 流覽至網站節點。 
    
6. 以滑鼠右鍵按一下站台，然後按一下 [編輯屬性]****。
    
7. 在左窗格中，按一下 [同盟路由]****。
    
8. 在 [**網站同盟路由指派**] 底下，選取 [**啟用 SIP 同盟**]，然後從清單中選取所列的商務用 Skype server 2019 Edge Server。 
  
9. 按一下 **[確定]** 關閉 **[編輯內容]** 頁面。 
    
     如有部署多個站台，請逐一在各個站台上完成此程序。 
    
## <a name="to-publish-edge-server-configuration-changes"></a>發行 Edge Server 的設定變更

1. 從 [**拓撲**產生器] 中，選取上方節點的**商務用 Skype 伺服器**。 
    
2. 從 [動作]**** 功能表中，選取 [發行拓撲]****，然後完成精靈。 
    
3. 等候部署中所有集區的 Active Directory 複寫作業開始。
    
    > [!NOTE]
    > 您可能會看到下列訊息：**警告：此拓撲包含一個以上的同盟 Edge Server。這可能會在將產品遷移至較新版本的產品時發生。在此情況下，只有一部 Edge Server 會積極用於同盟。驗證外部 DNS SRV 記錄是否指向正確的 Edge Server。如果您想要將多個同盟 Edge Server 同時部署為作用中（即不是遷移案例），請確認所有同盟夥伴皆使用商務用 Skype 伺服器。驗證外部 DNS SRV 記錄是否列出所有啟用同盟的 Edge Server。** 此為預期中的警告，可以不予理會。 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a>設定商務用 Skype Server 2019 Edge Server

1. 讓所有商務用 Skype Server 2019 Edge Server 線上。 
    
2. 更新外部防火牆路由規則或硬體負載平衡器設定，以將外部存取（通常是埠443）及同盟（通常是埠5061）的 SIP 流量傳送到商務用 Skype Server 2019 Edge Server，而不是舊版 Edge Server。
    
    > [!NOTE]
    > 如果您沒有硬體負載平衡器，您必須更新 DNS A 記錄的同盟，以解析為新的商務用 Skype Server Access Edge server。 若要以極少的中斷來達到此目的，請降低外部商務用 Skype Server Access Edge FQDN 的 TLL 值，以便在更新 DNS 以指向新的商務用 Skype Server Access Edge 時，會快速更新同盟和遠端存取。 
  
3. 從每一部 Edge Server 電腦停止**商務用 Skype Server Access Edge** 。 
    
4. 從每個舊版 Edge Server 電腦上，從 [系統**管理工具**] 中開啟 [**服務**] 小程式。
    
5. 在 [服務] 清單中，尋找**商務用 Skype Server Access Edge**。
    
6. 以滑鼠右鍵按一下服務名稱，然後選取 [停止]**** 停止服務。 
    
7. 將 [啟動類型] 設為 [停用]****。 
    
8. 按一下 [確定]****，以關閉 [屬性]**** 視窗。 
    

