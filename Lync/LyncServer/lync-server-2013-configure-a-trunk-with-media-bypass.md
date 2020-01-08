---
title: Lync Server 2013：使用 [旁路媒體] 設定主幹
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a trunk with media bypass
ms:assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398792(v=OCS.15)
ms:contentKeyID: 48184959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41f5f254dfd3ad63d3f6390f16837c777bd02a91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975602"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-with-media-bypass-in-lync-server-2013"></a>在 Lync Server 2013 中使用 [旁路媒體] 設定主幹

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-07_

請依照下列步驟來設定已啟用媒體旁路的幹線。 若要設定停用媒體旁路的幹線，請參閱[在 Lync Server 2013 中設定沒有媒體旁路的幹線](lync-server-2013-configure-a-trunk-without-media-bypass.md)。 如果您想要將部署的中繼伺服器數量減至最少，則可以使用 [媒體旁路]。 通常，會將中繼伺服器池部署在中央網站，它會控制分支網站上的閘道。 啟用「媒體旁路」可讓您從分支網站上的用戶端直接透過閘道從分支網站傳送公用交換電話網絡（PSTN）通話的媒體。 Lync Server 2013 出站通話路由及企業語音原則必須正確設定，才能將分支網站用戶端的 PSTN 呼叫路由至適當的閘道。

我們強烈建議您啟用 [媒體旁路]。 不過，在 SIP 主幹上啟用媒體旁路之前，請確認您的合格 SIP 幹線提供者支援媒體旁路，且能夠滿足成功啟用該案例的需求。 具體說來，提供者必須擁有貴組織內部網路中伺服器的 IP 位址。 如果提供者無法支援這個案例，媒體將無法成功。 如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的媒體旁路規劃](lync-server-2013-planning-for-media-bypass.md)。

<div>


> [!NOTE]  
> 媒體旁路將無法與每個公開交換電話網絡（PSTN）閘道、IP PBX 和會話邊界控制器（SBC）進行交互操作。 Microsoft 已經測試了一組 PSTN 閘道，並有已認證的合作夥伴，且已使用 Cisco IP-Pbx 進行了一些測試。 只有在整合通訊開啟互通性計畫（Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>）中所列的產品和版本，才能支援媒體略過。



</div>

下面所述的主幹設定會將套用至 trunks 指派這個幹線設定的一組參數組成。 您可以將特定的主幹設定設為全域（所有 trunks，而不會有更具體的網站或池配置），或是到網站或池中。 [池層級中繼] 設定是用來將特定主幹設定的範圍限定在單一干線中。

<span id="BKMK_ConfigTrunkMediaBypassSteps"></span>

<div>

## <a name="to-configure-a-trunk-with-media-bypass"></a>使用 [旁路媒體] 設定主幹

1.  以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**語音路由**]，然後按一下 [**幹線**設定]。

4.  在 [**幹線**設定] 頁面上，使用下列其中一種方法來設定幹線：
    
      - 按兩下現有的幹線（例如，**全域**幹線），以顯示 [**編輯主幹**設定] 對話方塊。
    
      - 按一下 [**新增**]，然後選取新主幹設定的範圍：
        
          - **網站主幹：** 從 [**選取網站**] 選擇此主幹設定的網站，然後按一下 **[確定]**。 請注意，如果已為網站建立中繼設定，網站就不會出現在 [**選取網站**] 中。 此主幹設定將會套用至網站中的所有 trunks。
        
          - **池主幹：** 選擇此幹線設定適用的主幹名稱。 這個幹線可以是根主幹或在拓撲建立器中定義的任何其他 trunks。 從 [**選取服務**] 中，按一下 **[確定]**。 請注意，如果已為特定主幹建立幹線設定，主幹不會出現在 [**選取服務**] 中。
    
    <div>
    

    > [!NOTE]  
    > 在您選取主幹設定的範圍之後，就無法變更它。<BR>[ <STRONG>Name</STRONG> ] （名稱）欄位會填入與中繼設定的關聯網站或服務名稱，且無法變更。

    
    </div>

5.  在**支援的最大早期對話方塊**中指定值。 這是公用交換電話網絡（PSTN）閘道、IP PBX 或 ITSP 會話邊界控制器（SBC）可接收傳送給轉送伺服器的邀請的數目上限。 預設值為20。
    
    <div>
    

    > [!NOTE]  
    > 變更此值前，請諮詢您的服務提供者或設備製造商，以取得系統功能的詳細資料。

    
    </div>

6.  選取下列其中一個**加密支援等級**選項：
    
      - **必要：** 安全即時傳輸通訊協定（SRTP）加密必須用來協助保護中繼伺服器與閘道或私人分支 exchange （PBX）之間的流量。
    
      - **選用：** 如果服務提供者或設備製造商支援，則會使用 SRTP 加密。
    
      - **不支援：** 服務提供者或設備製造商不支援 SRTP 加密，因此將無法使用。

7.  如果您想要媒體略過中繼伺服器以進行中繼對等處理，請選取 [**啟用媒體旁路**] 核取方塊。
    
    <div>
    

    > [!IMPORTANT]  
    > 若要讓媒體旁路功能順利運作，PSTN 閘道、IP PBX 或 ITSP 會話框線控制器必須支援某些功能。 如需詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-planning-for-media-bypass.md">Lync Server 2013 中的媒體旁路規劃</A>。

    
    </div>

8.  如果有已知的媒體端接點，請選取 [**集中式媒體處理**] 核取方塊（例如，媒體端接的 PSTN 閘道與 [信號終止] 一樣）。 如果主幹沒有已知的媒體端接點，請清除此核取方塊。

9.  如果乾線對等支援接收來自中繼伺服器的 SIP，請選取 [**啟用傳送參照至閘道**] 核取方塊。
    
    <div>
    

    > [!NOTE]  
    > 如果您在已選取 [<STRONG>啟用媒體旁路</STRONG>] 選項時停用此選項，則需要其他設定。 如果乾線對等不支援接收來自中繼伺服器和媒體旁路的 SIP 參照要求，您也必須執行<STRONG>new-cstrunkconfiguration</STRONG> Cmdlet 來停用使用中及保留通話的 RTCP，以支援媒體旁路的正確情況。 如需詳細資訊，請參閱<A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 管理命令</A>介面檔。<BR>或者，如果您想要將轉接來電轉接給媒體，且閘道不支援 SIP，請選取 [<STRONG>使用協力廠商通話的參照</STRONG>]。

    
    </div>

10. 可選若要啟用站間路由，請將 PSTN 使用記錄關聯並設定為此主幹設定。 與此幹線設定相關聯的 PSTN 用法，將會針對並非來自 Lync 端點之幹線的所有撥入電話套用。 若要管理與幹線設定相關聯的 PSTN 使用記錄，請使用下列其中一種方法：
    
      - 若要從企業語音部署中所有可用的 PSTN 使用記錄清單中選取一或多筆記錄，請按一下 [**選取**]。 醒目提示您要與此主幹設定關聯的記錄，然後按一下 **[確定]**。
    
      - 若要從此幹線設定中移除 PSTN 使用記錄，請選取該記錄，然後按一下 [**移除**]。
    
      - 若要定義新的 PSTN 使用記錄，並將它與此幹線設定關聯，請執行下列動作：
        
        1.  按一下 [**新增**]。
        
        2.  在 [**名稱**] 欄位中，為記錄指定唯一的描述性名稱。
            
            <div>
            

            > [!NOTE]  
            > PSTN 使用記錄名稱在企業語音部署中必須是唯一的。 在儲存記錄之後，[<STRONG>名稱</STRONG>] 欄位就無法進行編輯。

            
            </div>
        
        3.  使用下列其中一種方法來關聯及設定此 PSTN 使用記錄的路線：
            
              - 若要從企業語音部署中所有可用路由的清單中選取一或多個路由，請按一下 [**選取**]。 醒目提示您想要與此 PSTN 使用記錄產生關聯的路線，然後按一下 **[確定]**。
            
              - 若要從 PSTN 使用量記錄移除路由，請選取路由，然後按一下 [**移除**]。
            
              - 若要定義新的路由，並將它與此 PSTN 使用記錄建立關聯，請按一下 [**新增**]。 如需詳細資訊，請參閱[在 Lync Server 2013 中建立語音路由](lync-server-2013-create-a-voice-route.md)。
            
              - 若要編輯與此 PSTN 使用記錄相關聯的路線，請選取該路線，然後按一下 [**顯示詳細資料**]。 如需詳細資訊，請參閱[在 Lync Server 2013 中修改語音路線](lync-server-2013-modify-a-voice-route.md)。
        
        4.  按一下 [確定]****。
    
      - 若要編輯已與此幹線設定關聯的 PSTN 使用記錄，請執行下列動作：
        
        1.  選取您要編輯的 PSTN 使用量記錄，然後按一下 [**顯示詳細資料**]。
        
        2.  使用下列其中一種方法來關聯及設定此 PSTN 使用記錄的路線：
            
              - 若要從企業語音部署中所有可用路由的清單中選取一或多個路由，請按一下 [**選取**]。 醒目提示您想要與此 PSTN 使用記錄產生關聯的路線，然後按一下 **[確定]**。
            
              - 若要從 PSTN 使用量記錄移除路由，請選取路由，然後按一下 [**移除**]。
            
              - 若要定義新的路由，並將它與此 PSTN 使用記錄建立關聯，請按一下 [**新增**]。 如需詳細資訊，請參閱[在 Lync Server 2013 中建立語音路由](lync-server-2013-create-a-voice-route.md)。
            
              - 若要編輯與此 PSTN 使用記錄相關聯的路線，請選取該路線，然後按一下 [**顯示詳細資料**]。 如需詳細資訊，請參閱[在 Lync Server 2013 中修改語音路線](lync-server-2013-modify-a-voice-route.md)。
        
        3.  按一下 [確定]****。
    
    <div>
    

    > [!IMPORTANT]  
    > 將 PSTN 使用記錄與正在設定主幹的中繼伺服器對等相關聯是很重要的。 如果中繼伺服器對等是 PSTN 閘道或會話邊界控制器（SBC），強烈建議您不要將幹線設定與路由至 PSTN 目的地的 PSTN 使用記錄或任何其他透過 Lync 連接的任何其他下游系統關聯伺服器.

    
    </div>

11. 排列 PSTN 使用狀況記錄，以獲得最佳效能。 若要變更記錄在清單中的位置，請選取 PSTN 使用記錄，然後按一下向上或向下箭號。
    
    <div>
    

    > [!IMPORTANT]  
    > PSTN 使用記錄在幹線設定中的顯示順序非常重要。 Lync Server 會從上到下遍歷清單。

    
    </div>

12. 應選取 [**啟用 RTP 閉鎖**]，以針對網路位址轉譯（NAT）或防火牆以及支援閂鎖的 SBC 啟用旁路媒體。

13. 應選取 [**啟用轉寄通話記錄**]，以允許將通話記錄資訊傳送到中繼伺服器的閘道對等。

14. [**啟用前 p-已斷言身分識別的資料**] 請選取 [啟用 p 斷言身分識別（PAI）] 呼叫始發者資訊，以便在中繼伺服器端和閘道端（反之亦然）之間轉寄。

15. 若要啟用快速容錯移轉，請選取 [**啟用輸出路由容錯移轉計時器**]。 與此幹線關聯的閘道可以在處理撥出通話的10秒內發出通知。 如果中繼伺服器未收到此通知，就會將重新路由至另一個主幹。 在延遲可能會延遲回應時間的網路上，或閘道需要10秒以上的時間才能回應，就應該停用 [快速容錯移轉]。

16. 可選關聯並設定主幹的**通話數轉譯規則**。 這些翻譯規則會套用至撥出通話的電話號碼
    
      - 若要從企業語音部署中提供的所有翻譯規則清單中選擇一或多個規則，請按一下 [**選取**]。 在 [**選取翻譯規則**] 中，按一下您要與主幹建立關聯的規則，然後按一下 **[確定]**。
    
      - 若要定義新的翻譯規則，並將其與骨幹建立關聯，請按一下 [**新增**]。 如需有關定義新規則的詳細資料，請參閱在部署檔中的[Lync Server 2013 中定義翻譯規則](lync-server-2013-defining-translation-rules.md)。
    
      - 若要編輯已經與主幹建立關聯的翻譯規則，請按一下規則名稱，然後按一下 [**顯示詳細資料**]。 如需詳細資訊，請參閱在部署檔中的[Lync Server 2013 定義翻譯規則](lync-server-2013-defining-translation-rules.md)。
    
      - 若要複製現有的翻譯規則，以做為定義新規則的起點，請按一下規則名稱，然後按一下 [**複製**]，然後按一下 [**貼**上]。 如需詳細資訊，請參閱[在 Lync Server 2013 中定義翻譯規則](lync-server-2013-defining-translation-rules.md)。
    
      - 若要從主幹中移除翻譯規則，請將規則名稱醒目提示，然後按一下 [**移除**]。
    
    <div>
    

    > [!WARNING]  
    > 如果您已在關聯的中繼對等上設定翻譯規則，請不要將翻譯規則與幹線建立關聯，因為這兩個規則可能會衝突。

    
    </div>

17. 可選關聯並設定主幹的已**呼叫數位轉譯規則**。 翻譯規則會套用至撥出通話中呼叫的號碼。
    
      - 若要從企業語音部署中提供的所有翻譯規則清單中選擇一或多個規則，請按一下 [**選取**]。 在 [**選取翻譯規則**] 中，按一下您要與主幹建立關聯的規則，然後按一下 **[確定]**。
    
      - 若要定義新的翻譯規則，並將其與骨幹建立關聯，請按一下 [**新增**]。 如需有關定義新規則的詳細資料，請參閱在部署檔中的[Lync Server 2013 中定義翻譯規則](lync-server-2013-defining-translation-rules.md)。
    
      - 若要編輯已經與主幹建立關聯的翻譯規則，請按一下規則名稱，然後按一下 [**顯示詳細資料**]。 如需詳細資訊，請參閱在部署檔中的[Lync Server 2013 定義翻譯規則](lync-server-2013-defining-translation-rules.md)。
    
      - 若要複製現有的翻譯規則，以做為定義新規則的起點，請按一下規則名稱，然後按一下 [**複製**]，然後按一下 [**貼**上]。 如需詳細資訊，請參閱[在 Lync Server 2013 中定義翻譯規則](lync-server-2013-defining-translation-rules.md)。
    
      - 若要從主幹中移除翻譯規則，請將規則名稱醒目提示，然後按一下 [**移除**]。
    
    <div>
    

    > [!WARNING]  
    > 如果您已在關聯的中繼對等上設定翻譯規則，請不要將翻譯規則與幹線建立關聯，因為這兩個規則可能會衝突。

    
    </div>

18. 確定主幹的轉譯規則依正確順序排列。 若要變更規則在清單中的位置，請醒目提示 [規則名稱]，然後按一下向上或向下箭號。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 會從上到下遍歷翻譯規則清單，並使用與撥打的號碼相符的第一個規則。 如果您設定幹線，讓撥入的號碼可以符合多個翻譯規則，請確定更嚴格的規則，在限制性較低的規則之上排序。 例如，如果您已包含符合任何11位數的翻譯規則，以及只符合以 + 1425 開頭的11位數的翻譯規則，請確定符合任何11位數的規則，以更嚴格的<EM>規則排序。</EM>

    
    </div>

19. 當您完成設定主幹時，請按一下 **[確定]**。

20. 在 [**幹線**設定] 頁面上，按一下 [**認可**]，然後按一下 [**全部確認**]。
    
    <div>
    

    > [!NOTE]  
    > 每當您建立或修改幹線設定時，您都必須執行 [<STRONG>全部提交</STRONG>] 命令才能發佈設定變更。 如需詳細資訊，請參閱在 Operations 檔中<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">發佈 Lync Server 2013 中的語音路由設定的未決變更</A>。

    
    </div>

在您設定主幹之後，請選擇 [全域媒體旁路] 選項，繼續設定媒體旁路，如在部署檔中的[Lync Server 2013 的全域媒體旁路選項](lync-server-2013-global-media-bypass-options.md)中所述。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中設定沒有媒體旁路的主幹](lync-server-2013-configure-a-trunk-without-media-bypass.md)  


[在 Lync Server 2013 中設定媒體旁路](lync-server-2013-configure-media-bypass.md)  
[Lync Server 2013 中的全域媒體旁路選項](lync-server-2013-global-media-bypass-options.md)  


[在 Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

