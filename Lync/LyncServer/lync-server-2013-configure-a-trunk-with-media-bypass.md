---
title: Lync Server 2013：設定具有媒體旁路的主幹
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk with media bypass
ms:assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398792(v=OCS.15)
ms:contentKeyID: 48184959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 940470dc8b6ccb7563dede6e3deaa4f123d88858
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515720"
---
# <a name="configure-a-trunk-with-media-bypass-in-lync-server-2013"></a>在 Lync Server 2013 中設定含媒體旁路的主幹

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-07_

請遵循下列步驟，設定啟用媒體旁路的主幹。 若要設定停用媒體旁路的主幹，請參閱 [在 Lync Server 2013 中設定無媒體旁路的主幹](lync-server-2013-configure-a-trunk-without-media-bypass.md)。 當您想要將已部署的轉送伺服器數目降至最低時，媒體旁路很有用。 一般來說，轉送伺服器集區會部署在中央網站，它會控制分支網站上的閘道。 啟用媒體旁路允許公用交換電話網路的媒體 (PSTN) 來自分支網站用戶端的呼叫，以直接透過這些網站上的閘道來流向。 Lync Server 2013 輸出呼叫路由和 Enterprise Voice 原則必須正確設定，才能讓來自分支網站之用戶端的 PSTN 呼叫路由傳送至適當的閘道。

強烈建議您啟用媒體旁路。 不過，在 SIP 主幹上啟用媒體旁路之前，請先確認您合格的 SIP 主幹提供者支援媒體旁路，而且能夠滿足成功啟用此案例的需求。 具體而言，提供者必須具有組織內部網路中伺服器的 IP 位址。 如果提供者無法支援此案例，媒體旁路將會失敗。 如需詳細資訊，請參閱規劃檔中的 [規劃 Lync Server 2013 中的媒體旁路](lync-server-2013-planning-for-media-bypass.md) 。

<div>


> [!NOTE]  
> 媒體旁路不會與每一部公用交換電話網路 (PSTN) 閘道、IP-PBX 和會話邊界控制器 (SBC) 互動。 Microsoft 已測試一組 PSTN 閘道，並與認證的協力廠商 SBCs，並利用 Cisco IP PBXs 進行一些測試。 只有在整合通訊開啟互通性計畫– Lync Server at 上列出的產品及版本，才支援媒體旁路 <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> 。



</div>

如下所述的主幹設定群組一組套用至主幹指派此主幹設定的參數。 特定的主幹組態可涵蓋全域 (涵蓋至不具更明確網站或集區組態的所有主幹)，或涵蓋至網站或集區。 集區層級組態是用於將明確主幹組態涵蓋至單一主幹。

<span id="BKMK_ConfigTrunkMediaBypassSteps"></span>

<div>

## <a name="to-configure-a-trunk-with-media-bypass"></a>使用媒體旁路設定主幹

1.  以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[語音路由]**，再按一下 **[主幹組態]**。

4.  在 **[主幹組態]** 頁面上，使用下列其中一個方法設定主幹：
    
      - 按兩下現有主幹 (例如 **[通用]** 主幹)，顯示 **[編輯主幹組態]** 對話方塊。
    
      - 按一下 **[新增]**，然後選取新主幹組態：
        
          - **網站主幹：** 從 [ **選取網站**] 選擇此主幹設定的網站，然後按一下 **[確定]**。 請注意，如果已為某個網站建立主幹組態，則該網站不會出現在 **[選取站台]** 中。 此主幹組態將套用至網站中的所有主幹。
        
          - **集區主幹：** 選擇此主幹設定適用的主幹名稱。 這個主幹可以是根主幹或在拓撲產生器中定義的任何其他主幹。 從 [ **選取服務**] 中，按一下 **[確定]**。 請注意，如果已經針對特定主幹建立主幹組態，則該主幹就不會顯示在 **[選取服務]** 中。
    
    <div>
    

    > [!NOTE]  
    > 一旦選取主幹組態的範圍後，就無法變更。<BR><STRONG>[名稱]</STRONG> 欄位會預先填入主幹組態所關聯之網站或服務的名稱，此名稱無法變更。

    
    </div>

5.  在 **支援的最大早期對話方塊**中指定一個值。 這是公用交換電話網路 (PSTN) 閘道、IP-PBX 或 ITSP 會話邊界控制器 (SBC) 可以接收到它傳送給轉送伺服器的邀請數目上限。 預設值是 20。
    
    <div>
    

    > [!NOTE]  
    > 變更此值之前，請諮詢服務提供者或設備製造商，以取得系統功能的詳細資料。

    
    </div>

6.  選取下列其中一個 **[加密支援等級]** 選項：
    
      - **必要：** 安全即時傳輸通訊協定 (SRTP) 加密必須用來協助保護轉送伺服器和閘道或專用交換機 (PBX) 之間的流量。
    
      - **選用：** 如果服務提供者或設備製造商支援，就會使用 SRTP 加密。
    
      - **不支援：** SRTP 不支援服務提供者或設備製造商的加密，因此不會使用此加密。

7.  如果您想讓媒體略過轉送伺服器，以供主幹對等處理，請選取 [ **啟用媒體旁路** ] 核取方塊。
    
    <div>
    

    > [!IMPORTANT]  
    > 若要讓媒體旁路順利運作，PSTN 閘道、IP-PBX 或 ITSP 會話邊界控制器必須支援某些功能。 如需詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-planning-for-media-bypass.md">規劃 Lync Server 2013 中的媒體旁路</A> 。

    
    </div>

8.  如果有已知的媒體終端 (點，請選取 [ **集中式媒體處理** ] 核取方塊（例如，媒體端接系的 IP 位址與「終止」) 相同）。 如果主幹沒有已知的媒體終端點，請清除此核取方塊。

9.  如果主幹對等支援從轉送伺服器接收 SIP 參考要求，請選取 [ **啟用傳送參照至閘道** ] 核取方塊。
    
    <div>
    

    > [!NOTE]  
    > 如果在選取 [ <STRONG>啟用媒體旁路</STRONG> ] 選項時停用此選項，則需要其他設定。 若主幹對等不支援從轉送伺服器接收 SIP 參考要求和媒體旁路，您也必須執行 <STRONG>Set-CsTrunkConfiguration</STRONG> Cmdlet 以停用使用中和保留通話的 RTCP，以便支援媒體旁路的適當狀況。 如需詳細資訊，請參閱 <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 管理命令</A> 介面檔。<BR>或者，您也可以選取 [ <STRONG>使用協力廠商通話控制啟用參考</STRONG> ]，如果您想要將轉接來電轉接到媒體略過，而閘道不支援 SIP 參考要求。

    
    </div>

10. (選用) 若要啟用主幹間的路由，請關聯至此主幹組態並設定其 PSTN 使用方式記錄。與此主幹組態相關聯的 PSTN 使用方式，將會套用至整個主幹中並非由 Lync 端點產生的所有來電。若要管理與主幹組態關聯的 PSTN 使用方式記錄，請使用下列其中一種方法：
    
      - 若要從 Enterprise Voice 部署中所有可用的 PSTN 使用方式記錄清單中選取一或多筆記錄，請按一下 [ **選取**]。 反白顯示您要與此主幹組態建立關聯的記錄，然後按一下 **[確定]**。
    
      - 若要從此主幹組態移除 PSTN 使用方式記錄，請選取該記錄然後按一下 **[移除]**。
    
      - 若要定義新的 PSTN 使用方式記錄，並建立與此主幹組態的關聯，請執行下列動作：
        
        1.  按一下 **[新增]**。
        
        2.  在 **[名稱]** 欄位中，指定該記錄的唯一描述性名稱。
            
            <div>
            

            > [!NOTE]  
            > PSTN 使用方式記錄名稱必須是 Enterprise Voice 部署內的唯一名稱。儲存記錄之後，就無法編輯 <STRONG>[名稱]</STRONG> 欄位。

            
            </div>
        
        3.  使用下列其中一種方法，關聯至此 PSTN 使用方式記錄並設定其路由：
            
              - 若要從 Enterprise Voice 部署中所有可用路由的清單中選取一個或多個路由，請按一下 [ **選取**]。 反白顯示您要與此 PSTN 使用方式記錄相關聯的路由，然後按一下 **[確定]**。
            
              - 若要從 PSTN 使用方式記錄移除路由，請選取該路由，然後按一下 **[移除]**。
            
              - 若要定義新路由，並將其關聯至此 PSTN 使用記錄，請按一下 **[新增]**。 如需詳細資訊，請參閱 [Create a voice route In Lync Server 2013](lync-server-2013-create-a-voice-route.md)。
            
              - 若要編輯與此 PSTN 使用方式記錄相關聯的路由，請選取該路由，然後按一下 **[顯示詳細資料]**。 如需詳細資訊，請參閱 [Modify a voice route In Lync Server 2013](lync-server-2013-modify-a-voice-route.md)。
        
        4.  按一下 **[確定]**。
    
      - 若要編輯已經與此主幹組態建立關聯的 PSTN 使用方式記錄，請執行下列動作：
        
        1.  選取您要編輯的 PSTN 使用方式記錄，然後按一下 **[顯示詳細資料]**。
        
        2.  使用下列其中一種方法，關聯至此 PSTN 使用方式記錄並設定其路由：
            
              - 若要從 Enterprise Voice 部署中所有可用路由的清單中選取一個或多個路由，請按一下 [ **選取**]。 反白顯示您要與此 PSTN 使用方式記錄相關聯的路由，然後按一下 **[確定]**。
            
              - 若要從 PSTN 使用方式記錄移除路由，請選取該路由，然後按一下 **[移除]**。
            
              - 若要定義新路由，並將其關聯至此 PSTN 使用記錄，請按一下 **[新增]**。 如需詳細資訊，請參閱 [Create a voice route In Lync Server 2013](lync-server-2013-create-a-voice-route.md)。
            
              - 若要編輯與此 PSTN 使用方式記錄相關聯的路由，請選取該路由，然後按一下 **[顯示詳細資料]**。 如需詳細資訊，請參閱 [Modify a voice route In Lync Server 2013](lync-server-2013-modify-a-voice-route.md)。
        
        3.  按一下 [確定]****。
    
    <div>
    

    > [!IMPORTANT]  
    > 將 PSTN 使用方式記錄與所設定之主幹相關聯的轉送伺服器對等相關聯是很重要的。 若轉送伺服器對等是 PSTN 閘道或會話邊界控制器 (SBC) ，強烈建議您不要將主幹設定相關聯至 PSTN 使用方式記錄，該記錄會路由傳送至 PSTN 目的地或透過 Lync Server 連接的任何其他下游系統。

    
    </div>

11. 請排列 PSTN 使用方式記錄以達到最佳效能。若要變更記錄在清單中的位置，請選取 PSTN 使用記錄，然後按一下向上或向下箭號。
    
    <div>
    

    > [!IMPORTANT]  
    > PSTN 使用方式記錄列示在主幹組態中的順序非常重要。 Lync Server 從上到上，從上到上的遍歷清單。

    
    </div>

12. 應該選取 [**啟用 RTP**鎖定]，以啟用網路位址轉譯之後用戶端的旁路媒體（ (NAT) 或防火牆，以及支援閉鎖的 SBC）。

13. 應該選取 [**啟用轉接來電記錄**]，以啟用將通話記錄資訊傳送至轉送伺服器的閘道對等功能。

14. 您應該選取 [**啟用轉寄 P-Asserted-Identity 資料**]，以啟用 P-ASSERTED-IDENTITY (PAI) 呼叫發信方資訊，以便在轉送伺服器端與閘道端 (之間轉送，反之亦然。

15. 您應選取 **[啟用輸出路由容錯移轉計時器]** 才能啟用快速容錯移轉。 由於與此主幹相關聯的閘道正在處理撥出電話，所以可以在 10 秒內發出通知。 若轉送伺服器未收到此通知，則會進行重新路由至另一個主幹。 在延遲可能遞延回應時間的網路上或是閘道回應時間在 10 秒以上者，應停用快速容錯移轉。

16. (選用) 建立與主幹的關聯並設定其 **[撥號轉譯規則]**。 這些轉譯規則適用於撥出電話的撥打號碼
    
      - 若要從 Enterprise Voice 部署中所有可用轉譯規則的清單中選擇一個或多個規則，請按一下 [ **選取**]。 在 **[選取轉譯規則]** 中，按一下您要建立關聯的主幹，然後按一下 **[確定]**。
    
      - 若要定義新的轉譯規則並建立其與主幹的關聯，請按一下 **[新增]**。 如需定義新規則的詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md) 。
    
      - 若要編輯已與主幹建立關聯的轉譯規則，按一下規則名稱，然後按一下 **[顯示詳細資料]**。 如需詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md) 。
    
      - 若要複製現有轉譯規則，以用來作為定義新規則時的起點，請按一下規則名稱，再按一下 **[複製]**，然後按一下 **[貼上]**。 如需詳細資訊，請參閱 [在 Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md)。
    
      - 若要從主幹移除轉譯規則，請反白顯示該規則名稱並按一下 **[移除]**。
    
    <div>
    

    > [!WARNING]  
    > 如果您已在關聯的主幹對等上設定轉譯規則，請勿再將轉譯規則與主幹建立關聯，因為這兩個規則可能會產生衝突。

    
    </div>

17. (選用) 建立與主幹的關聯並設定其 **[撥號轉譯規則]**。這些轉譯規則適用於撥出電話的撥打號碼。
    
      - 若要從 Enterprise Voice 部署中所有可用轉譯規則的清單中選擇一個或多個規則，請按一下 [ **選取**]。 在 **[選取轉譯規則]** 中，按一下您要建立關聯的主幹，然後按一下 **[確定]**。
    
      - 若要定義新的轉譯規則並建立其與主幹的關聯，請按一下 **[新增]**。 如需定義新規則的詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md) 。
    
      - 若要編輯已與主幹建立關聯的轉譯規則，按一下規則名稱，然後按一下 **[顯示詳細資料]**。 如需詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md) 。
    
      - 若要複製現有轉譯規則，以用來作為定義新規則時的起點，請按一下規則名稱，再按一下 **[複製]**，然後按一下 **[貼上]**。 如需詳細資訊，請參閱 [在 Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md)。
    
      - 若要從主幹移除轉譯規則，請反白顯示該規則名稱並按一下 **[移除]**。
    
    <div>
    

    > [!WARNING]  
    > 如果您已在相關聯的主幹對等上設定轉譯規則，則請勿將轉譯規則與主幹建立關聯，因為兩種規則可能會衝突。

    
    </div>

18. 請確定主幹的轉譯規則依正確的順序排列。 若要變更規則在清單中的位置，請反白顯示規則名稱，然後按一下向上或向下箭號。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 會從左上部開始轉譯轉譯規則清單，並使用符合撥號號碼的第一個規則。 如果您設定的主幹會使撥號號碼符合不只一個轉譯規則，請確定限制較多的規則排在限制較少的規則上方。 例如，如果您包含的轉譯規則中有一個規則符合所有 11 位數號碼，另有一個轉譯規則僅符合開頭為 +1425 的 11 位數號碼，則請確定符合所有 11 位數號碼的規則排在另一個限制較多規則的<EM>下方</EM>。

    
    </div>

19. 完成主幹的設定時，請按一下 **[確定]**。

20. 在 **[主幹組態]** 頁面上，按一下 **[認可]**，再按一下 **[全部認可]**。
    
    <div>
    

    > [!NOTE]  
    > 只要建立或修改主幹組態後，都應執行 <STRONG>[全部認可]</STRONG> 命令以發行組態變更。 如需詳細資訊，請參閱 Operations 檔中的在 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中發佈擱置的變更至語音路由</A> 設定。

    
    </div>

設定主幹之後，請選擇通用媒體旁路選項，繼續設定媒體旁路，如部署檔中的 [ [Lync Server 2013 中的全域媒體旁路選項](lync-server-2013-global-media-bypass-options.md) 所述。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中設定無媒體旁路的主幹](lync-server-2013-configure-a-trunk-without-media-bypass.md)  


[在 Lync Server 2013 中設定媒體旁路](lync-server-2013-configure-media-bypass.md)  
[Lync Server 2013 中的全域媒體旁路選項](lync-server-2013-global-media-bypass-options.md)  


[在 Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

