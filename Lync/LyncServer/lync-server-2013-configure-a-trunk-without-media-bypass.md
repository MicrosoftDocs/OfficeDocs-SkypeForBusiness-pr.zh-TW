---
title: Lync Server 2013：設定無媒體旁路的主幹
description: Lync Server 2013：設定不含媒體旁路的主幹。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk without media bypass
ms:assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425831(v=OCS.15)
ms:contentKeyID: 48183825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 586ab4f283034c94bd7cb0179d73a963cad88347
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555959"
---
# <a name="configure-a-trunk-without-media-bypass-in-lync-server-2013"></a>在 Lync Server 2013 中設定無媒體旁路的主幹

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-24_

如果您想將主幹設定為停用媒體旁路，請遵循下列步驟。 如果您想要設定主幹以啟用媒體旁路，請參閱 [在 Lync Server 2013 中使用媒體旁路設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)。

如以下所述，主幹組態會將一組參數群組在一起，該組參數適用於指派此主幹組態的主幹。特定的主幹組態可涵蓋全域 (涵蓋至不具更明確網站或集區組態的所有主幹)，或涵蓋至網站或集區。集區層級組態是用於將明確主幹組態涵蓋至單一主幹。

<span id="BKMK_ConfigTrunkGenericSteps"></span>

<div>

## <a name="to-configure-a-trunk-without-media-bypass"></a>設定沒有媒體旁路的主幹

1.  以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[語音路由]**，再按一下 **[主幹組態]**。

4.  在 **[主幹組態]** 頁面上，使用下列其中一個方法設定主幹：
    
      - 按兩下現有主幹 (例如 **[通用]** 主幹)，顯示 **[編輯主幹組態]** 對話方塊。
    
      - 按一下 **[新增]**，然後選取新主幹組態：
        
          - **網站主幹：** 在 [ **選取網站** ] 中選擇此主幹設定的網站，然後按一下 **[確定]**。 請注意，如果已為某個網站建立主幹組態，則該網站不會出現在 **[選取站台]** 中。 此主幹組態將套用至網站中的所有主幹。
        
          - **集區主幹：** 在 [ **選取服務** ] 中選擇此主幹設定所套用的主幹名稱，然後按一下 **[確定]**。 這個主幹可以是根主幹，或在拓撲產生器中定義的任何其他主幹。 請注意，如果已經針對特定主幹建立主幹組態，則該主幹就不會顯示在 **[選取服務]** 中。
    
    <div>
    

    > [!NOTE]  
    > 一旦選取主幹組態的範圍後，就無法變更。<BR><STRONG>[名稱]</STRONG> 欄位會預先填入主幹組態所關聯之網站或服務的名稱，此名稱無法變更。

    
    </div>

5.  選取下列其中一個 **[加密支援等級]** 選項：
    
      - **必要：** 安全即時傳輸通訊協定 (SRTP) 加密必須用來協助保護轉送伺服器和閘道或專用交換機 (PBX) 之間的流量。
    
      - **選用：** 如果服務提供者或設備製造商支援，就會使用 SRTP 加密。
    
      - **不支援：** SRTP 不支援服務提供者或設備製造商的加密，因此不會使用此加密。

6.  確定清除 **[啟用媒體旁路]** 核取方塊。

7.  如果有已知的媒體終端點 (例如公用交換電話網路 (PSTN) 閘道，因為媒體終端的 IP 與訊號終端相同)，則選取 **[集中式媒體處理]** 核取方塊。如果主幹沒有已知的媒體終端點，請清除此核取方塊。

8.  如果主幹對等支援從轉送伺服器接收 SIP 參考要求，請選取 [ **啟用傳送參照至閘道** ] 核取方塊。

9.  (選用) 若要啟用主幹間的路由，請關聯至此主幹組態並設定其 PSTN 使用方式記錄。與此主幹組態相關聯的 PSTN 使用方式，將會套用至整個主幹中並非由 Lync 端點產生的所有來電。若要管理與主幹組態關聯的 PSTN 使用方式記錄，請使用下列其中一種方法：
    
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

10. 請排列 PSTN 使用方式記錄以達到最佳效能。若要變更記錄在清單中的位置，請選取 PSTN 使用記錄，然後按一下向上或向下箭號。
    
    <div>
    

    > [!IMPORTANT]  
    > PSTN 使用方式記錄列示在主幹組態中的順序非常重要。 Lync Server 從上到上，從上到上的遍歷清單。

    
    </div>

11. 您應該選取 **[啟用 RTP 栓]** 才能啟用位於 NAT 或防火牆後方的用戶端旁路媒體，以及支援栓的 SBC。

12. 應該選取 [**啟用轉接來電記錄**]，以啟用將通話記錄資訊傳送至轉送伺服器的閘道對等功能。

13. [**啟用轉寄 P-Asserted-Identity 資料**] 選取此選項，即可啟用 PAI 呼叫發起者資訊，以便在轉送伺服器端與閘道端 (之間轉送，反之亦然) （如有）。

14. 您應選取 **[啟用輸出路由容錯移轉計時器]** 才能啟用快速容錯移轉。 由於與此主幹相關聯的閘道正在處理撥出電話，所以可以在 10 秒內發出通知。 若轉送伺服器未收到此通知，則會進行重新路由至另一個主幹。 在延遲可能遞延回應時間的網路上或是閘道回應時間在 10 秒以上者，應停用快速容錯移轉。

15. (選用) 建立與主幹的關聯並設定其 **[撥號轉譯規則]**。 這些轉譯規則適用於撥出電話的撥打號碼
    
      - 若要從 Enterprise Voice 部署中所有可用轉譯規則的清單中選擇一個或多個規則，請按一下 [ **選取**]。 在 **[選取轉譯規則]** 中，按一下您要建立關聯的主幹，然後按一下 **[確定]**。
    
      - 若要定義新的轉譯規則並建立其與主幹的關聯，請按一下 **[新增]**。 如需定義新規則的詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md) 。
    
      - 若要編輯已與主幹建立關聯的轉譯規則，按一下規則名稱，然後按一下 **[顯示詳細資料]**。 如需詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md) 。
    
      - 若要複製現有轉譯規則，以用來作為定義新規則時的起點，請按一下規則名稱，再按一下 **[複製]**，然後按一下 **[貼上]**。 如需詳細資訊，請參閱 [在 Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md)。
    
      - 若要從主幹移除轉譯規則，請反白顯示該規則名稱並按一下 **[移除]**。
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="安全" alt="security" />安全性附注：</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>如果您已在關聯的主幹對等上設定轉譯規則，請勿再將轉譯規則與主幹建立關聯，因為這兩個規則可能會產生衝突。</td>
    </tr>
    </tbody>
    </table>
    
    </div>

16. (選用) 建立與主幹的關聯並設定其 **[撥號轉譯規則]**。這些轉譯規則適用於撥出電話的撥打號碼。
    
      - 若要從 Enterprise Voice 部署中所有可用轉譯規則的清單中選擇一個或多個規則，請按一下 [ **選取**]。 在 **[選取轉譯規則]** 中，按一下您要建立關聯的主幹，然後按一下 **[確定]**。
    
      - 若要定義新的轉譯規則並建立其與主幹的關聯，請按一下 **[新增]**。 如需定義新規則的詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md) 。
    
      - 若要編輯已與主幹建立關聯的轉譯規則，按一下規則名稱，然後按一下 **[顯示詳細資料]**。 如需詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md) 。
    
      - 若要複製現有轉譯規則，以用來作為定義新規則時的起點，請按一下規則名稱，再按一下 **[複製]**，然後按一下 **[貼上]**。 如需詳細資訊，請參閱 [在 Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md)。
    
      - 若要從主幹移除轉譯規則，請反白顯示該規則名稱並按一下 **[移除]**。
    
    <div>
    

    > [!WARNING]  
    > 如果您已在相關聯的主幹對等上設定轉譯規則，則請勿將轉譯規則與主幹建立關聯，因為兩種規則可能會衝突。

    
    </div>

17. 請確定主幹的轉譯規則依正確的順序排列。 若要變更規則在清單中的位置，請反白規則名稱，然後按向上或向下箭頭。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 會從左上部開始轉譯轉譯規則清單，並使用符合撥號號碼的第一個規則。 如果您設定的主幹會使撥號號碼符合不只一個轉譯規則，請確定限制較多的規則排在限制較少的規則上方。 例如，如果您包含的轉譯規則中有一個規則符合所有 11 位數號碼，另有一個轉譯規則僅符合開頭為 +1425 的 11 位數號碼，則請確定符合所有 11 位數號碼的規則排在另一個限制較多規則的<EM>下方</EM>。

    
    </div>

18. 完成主幹的設定時，請按一下 **[確定]**。

19. 在 **[主幹組態]** 頁面上，按一下 **[認可]**，再按一下 **[全部認可]**。
    
    <div>
    

    > [!NOTE]  
    > 只要建立或修改主幹組態後，都應執行 <STRONG>[全部認可]</STRONG> 命令以發行組態變更。 如需詳細資訊，請參閱 Operations 檔中的在 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中發佈擱置的變更至語音路由</A> 設定。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中設定含媒體旁路的主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[在 Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

