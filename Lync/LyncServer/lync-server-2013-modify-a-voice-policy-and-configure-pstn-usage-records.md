---
title: Lync Server 2013：修改語音原則和設定 PSTN 使用方式記錄
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a voice policy and configure PSTN usage records
ms:assetid: 6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398511(v=OCS.15)
ms:contentKeyID: 48184419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e198158c60b7605ee78179e4a4e74c86791dfa1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a>在 Lync Server 2013 中修改語音原則和設定 PSTN 使用方式記錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

如果您想要修改語音原則，請遵循下列步驟。 如果您想要建立新的語音原則，請參閱[在 Lync Server 2013 中建立語音原則和設定 PSTN 使用方式記錄](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)，以取得此過程。

<div>


> [!NOTE]  
> 如果將使用者指派給沒有相關聯公用交換電話網路 (PSTN) 使用方式記錄的語音原則，則該使用者無法撥出電話。 如需您 Enterprise Voice 部署中所有可用的 PSTN 使用方式記錄清單，並查看其屬性，請參閱<A href="lync-server-2013-view-pstn-usage-records.md">在 Lync Server 2013 中查看 PSTN 使用方式記錄</A>。



</div>

<div>

## <a name="to-modify-a-voice-policy"></a>若要修改語音原則

1.  以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱[在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，依序按一下 **[語音路由]** 和 **[語音原則]**。

4.  在 **[語音原則]** 頁面上，按兩下語音原則名稱。
    
    <div>
    

    > [!NOTE]  
    > 範圍和名稱在語音原則建立時就已設定。您無法加以變更。

    
    </div>

5.  (選用) 在 **[編輯語音原則]** 中，輸入語音原則的其他描述性資訊。

6.  選取或清除下列核取方塊以啟用或停用每個 **[撥號功能]**：
    
      - **[語音信箱逸出]** 可在設定為同時響鈴，且手機在關機、電池電力耗盡或在收訊範圍之外時，防止通話立即路由傳送至使用者的行動電話語音信箱系統。
        
        <div>
        

        > [!NOTE]  
        > 此功能僅可透過 Lync Server 管理命令介面進行設定

        
        </div>
    
      - **[來電轉接]** 可讓使用者將來電轉接到其他電話和用戶端裝置。 Lync Server 2013 為來電轉接提供更為廣泛的設定選項。 例如，如果組織不想讓來電向外轉接到 PSTN，系統管理員可套用特殊語音原則以部署此限制。 預設為啟用。
    
      - **[委派]** 可讓使用者指定其他使用者，來代表他們撥號和接聽電話。 在 Lync Server 2013 中，代理人可以設定同時震鈴，讓來電者能夠撥打所有代理人同時震鈴的目標。 這樣可在回應撥至主管的通話時給予代理人更大的彈性。 預設為啟用。
    
      - **[通話轉接]** 可讓使用者將通話轉接給其他使用者。預設為啟用。
    
      - **[通話駐留]** 可讓使用者將通話駐留成保留狀態，然後由不同電話或用戶端接聽通話。預設為停用。
    
      - **[同時響鈴]** 可讓來電在更多電話 (例如，行動電話) 或其他端點裝置上發出鈴聲。 Lync Server 2013 為同時震鈴的設定選項提供了極大範圍的設定。 預設為啟用。
    
      - **[小組通話]** 可讓所定義小組的使用者接聽該小組其他成員的通話。預設為啟用。
    
      - **[PSTN 重新路由]** 可在 WAN 擁塞或無法使用時，將被指派此原則的使用者撥打給其他企業使用者的電話，以公用交換電話網路 (PSTN) 重新路由。預設為啟用。
    
      - **[頻寬原則覆寫]** 可讓系統管理員覆寫特定使用者的通話許可控制 (CAC) 原則決策。預設為停用。
        
        <div>
        

        > [!NOTE]  
        > 系統只會針對撥入給使用者的來電，而不會針對使用者撥出的電話覆寫此原則。工作階段建立之後，便可準確地記錄頻寬使用量。請謹慎使用此設定。

        
        </div>
    
      - **[惡意通話追蹤]** 可讓使用者使用用戶端 UI 來回報惡意通話 (如炸彈威脅)，此舉會在詳細通話記錄 (CDR) 中以旗標標記通話。預設為停用。

7.  若要為此語音原則來關聯及設定 PSTN 使用方式記錄，請執行下列任何一項動作：
    
      - 若要從您 Enterprise Voice 部署中所有可用的 PSTN 使用方式記錄清單中選擇一或多個記錄，請按一下 **[選取]**。反白顯示您想要與此語音原則關聯的記錄，然後按一下 **[確定]**。
    
      - 若要從此語音原則中移除 PSTN 使用方式記錄，請反白顯示記錄，然後按一下 **[移除]**。
    
      - 若要定義新的 PSTN 使用方式記錄，並將它與此語音原則關聯，請執行下列動作：
        
        1.  按一下 **[新增]**。
        
        2.  在 **[名稱]** 欄位中，輸入記錄的唯一描述性名稱。例如，您可能會想要針對 Redmond 的全職員工建立一個名為 **Redmond** 的 PSTN 使用方式記錄，並針對臨時員工建立另一個名為 **RedmondTemps** 的記錄。
            
            <div>
            

            > [!NOTE]  
            > 在 Enterprise Voice 部署內，PSTN 使用方式記錄名稱必須是唯一的。儲存記錄之後，就無法編輯 <STRONG>[名稱]</STRONG> 欄位。

            
            </div>
        
        3.  使用下列任一方法針對此 PSTN 使用方式記錄建立關聯及設定路由：
            
              - 若要從 Enterprise Voice 部署中所有可用路由的清單中選擇一個或多個路由，請按一下 **[選取]**，並反白顯示想要與此 PSTN 使用方式記錄建立關聯的路由，然後按一下 **[確定]**。
            
              - 若要從 PSTN 使用方式記錄中移除路由，請反白顯示路由，然後按一下 **[移除]**。
            
              - 若要定義新的路由，並將它與此 PSTN 使用方式記錄關聯，請按一下 **[新增]**。 如需詳細資訊，請參閱[Create a voice route In Lync Server 2013](lync-server-2013-create-a-voice-route.md)。
            
              - 若要編輯已與此 PSTN 使用方式記錄關聯的路由，請反白顯示路由，然後按一下 **[顯示詳細資料]**。 如需詳細資訊，請參閱[Modify a voice route In Lync Server 2013](lync-server-2013-modify-a-voice-route.md)。
        
        4.  按一下 **[確定]**。
    
      - 若要編輯已經與此語音原則建立關聯的 PSTN 使用方式記錄，請執行下列動作：
        
        1.  反白顯示希望編輯的 PSTN 使用方式記錄，然後按一下 **[顯示詳細資料]**。
        
        2.  使用下列任何一種方法來關聯及設定此 PSTN 使用方式記錄的路由：
            
              - 若要從您 Enterprise Voice 部署中所有可用的路由清單中選擇一或多個路由，請按一下 **[選取]**，反白顯示您想要與此 PSTN 使用方式記錄關聯的路由，然後按一下 **[確定]**。
            
              - 若要從此 PSTN 使用記錄移除路由，請反白顯示路由，然後按一下 **[移除]**。
            
              - 若要定義新的路由，並將它與此 PSTN 使用方式記錄關聯，請按一下 **[新增]**。 如需詳細資訊，請參閱[Create a voice route In Lync Server 2013](lync-server-2013-create-a-voice-route.md)。
            
              - 若要編輯已與此 PSTN 使用方式記錄關聯的路由，請反白顯示路由，然後按一下 **[顯示詳細資料]**。 如需詳細資訊，請參閱[Modify a voice route In Lync Server 2013](lync-server-2013-modify-a-voice-route.md)。
        
        3.  按一下 **[確定]**。

8.  排列 PSTN 使用方式記錄，以獲得最佳效能。若要變更清單中某筆記錄的位置，請反白顯示記錄名稱，然後按一下向上或向下箭頭。
    
    <div>
    

    > [!NOTE]  
    > PSTN 使用方式記錄列在語音原則中的順序十分重要。 Lync Server 會從上而往上，遍歷清單。 建議您依使用頻率來組織清單，例如：RedmondLocal、RedmondLongDist、RedmondInternational 和 RedmondBackup。

    
    </div>

9.  若要針對此語音原則中的來電轉接和同時鈴響建立關聯並設定 PSTN 使用方式記錄，請執行下列其中一項作業：
    
      - 若要依據此語音原則針對來電轉接和同時響鈴使用相同的 PSTN 使用方式記錄，請從下拉式功能表中選取 **[使用通話 PSTN 使用方式的路由]** 選項。
    
      - 若要僅允許對內部 Lync 使用者進行來電轉接和同時響鈴，請選取 [僅從下拉式功能表**傳送至內部 lync 使用者**]。 通話不會轉接至外部 PSTN 號碼。
    
      - 若要針對用於此語音原則之外的來電轉接和同時響鈴指定其他 PSTN 使用方式記錄，請從下拉式功能表中選取 **[使用自訂 PSTN 使用方式的路由]** 選項。此選項會特別針對來電轉接和同時響鈴顯示控制項，用來選取現有 PSTN 使用方式記錄或建立新的 PSTN 使用方式記錄。
        
          - 若要針對來電轉接和同時響鈴從所有可用的 PSTN 使用方式記錄清單中選擇一筆或多筆記錄，請按一下 **[選取]**。反白顯示想要與此來電轉接和同時鈴響原則關聯的記錄，然後按一下 **[確定]**。
        
          - 若要從此來電轉接和同時鈴響原則移除 PSTN 使用方式記錄，請反白顯示記錄，然後按一下 **[移除]**。
        
          - 若要定義新的 PSTN 使用方式記錄，並建立其與此來電轉接和同時鈴響的關聯，請執行下列動作：
            
            1.  按一下 **[新增]**。
            
            2.  在 **[名稱]** 欄位中，輸入記錄的唯一描述性名稱。
                
                <div>
                

                > [!NOTE]  
                > PSTN 使用方式記錄名稱必須是 Enterprise Voice 部署內的唯一名稱。儲存記錄之後，就無法編輯 <STRONG>[名稱]</STRONG> 欄位。

                
                </div>
            
            3.  使用下列任一方法針對此 PSTN 使用方式記錄建立關聯及設定路由：
                
                  - 若要從 Enterprise Voice 部署中所有可用路由的清單中選擇一個或多個路由，請按一下 **[選取]**，並反白顯示想要與此 PSTN 使用方式記錄建立關聯的路由，然後按一下 **[確定]**。
                
                  - 若要從 PSTN 使用方式記錄中移除路由，請反白顯示路由，然後按一下 **[移除]**。
                
                  - 若要定義新的路由，並將它與此 PSTN 使用方式記錄關聯，請按一下 **[新增]**。 如需詳細資訊，請參閱[Create a voice route In Lync Server 2013](lync-server-2013-create-a-voice-route.md)。
                
                  - 若要編輯已經與此 PSTN 使用方式記錄建立關聯的路由，請反白顯示路由，然後按一下 **[顯示詳細資料]**。 如需詳細資訊，請參閱[Modify a voice route In Lync Server 2013](lync-server-2013-modify-a-voice-route.md)。
            
            4.  按一下 **[確定]**。
        
          - 若要編輯已經與此語音原則建立關聯的 PSTN 使用方式記錄，請執行下列動作：
            
            1.  反白顯示希望編輯的 PSTN 使用方式記錄，然後按一下 **[顯示詳細資料]**。
            
            2.  使用下列任一方法，針對此 PSTN 使用方式記錄來建立關聯及設定路由：
                
                  - 若要從 Enterprise Voice 部署中所有可用路由的清單中選擇一個或多個路由，請按一下 **[選取]**，並反白顯示想要與此 PSTN 使用方式記錄關聯的路由，然後按一下 **[確定]**。
                
                  - 若要從此 PSTN 使用方式記錄中移除路由，請反白顯示路由，然後按一下 **[移除]**。
                
                  - 若要定義新的路由，並將它與此 PSTN 使用方式記錄關聯，請按一下 **[新增]**。 如需詳細資訊，請參閱[Create a voice route In Lync Server 2013](lync-server-2013-create-a-voice-route.md)。
                
                  - 若要編輯已與此 PSTN 使用方式記錄關聯的路由，請反白顯示路由，然後按一下 **[顯示詳細資料]**。 如需詳細資訊，請參閱[Modify a voice route In Lync Server 2013](lync-server-2013-modify-a-voice-route.md)。
            
            3.  按一下 **[確定]**。

10. (選用) 輸入號碼以測試語音原則，然後按一下 **[執行]**。測試結果會顯示在 **[要測試的轉譯號碼]** 下方。
    
    <div>
    

    > [!NOTE]  
    > 您可以儲存尚未通過測試的語音原則，稍後再加以重新設定。 如需詳細資訊，請參閱<A href="lync-server-2013-test-voice-routing.md">Test voice routing In Lync Server 2013</A>。

    
    </div>

11. 按一下 **[確定]**。

12. 在 **[語音原則]** 頁面上，依序按一下 **[認可]** 和 **[全部認可]**。
    
    <div>
    

    > [!NOTE]  
    > 只要建立或修改語音原則，就必須執行 <STRONG>[全部認可]</STRONG> 命令來發行設定變更。 如需詳細資訊，請參閱 Operations 檔中的在<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中發佈擱置的變更至語音路由</A>設定。

    
    </div>

13. (選用) [語音信箱] 逸出會偵測使用者的行動電話語音信箱是否立即接聽來電，並中斷與行動電話語音信箱的連線。 這樣可讓來電繼續在使用者的其他端點上響鈴，讓使用者有機會接聽來電。 如需如何設定語音信箱原則的詳細資訊，請參閱[在 Lync Server 2013 中設定語音信箱轉義](lync-server-2013-configuring-voice-mail-escape.md)。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中建立語音原則和設定 PSTN 使用方式記錄](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[在 Lync Server 2013 中查看 PSTN 使用方式記錄](lync-server-2013-view-pstn-usage-records.md)  
[在 Lync Server 2013 中建立語音路由](lync-server-2013-create-a-voice-route.md)  
[在 Lync Server 2013 中修改語音路由](lync-server-2013-modify-a-voice-route.md)  
[在 Lync Server 2013 中將擱置的變更發佈至語音路由設定](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[在 Lync Server 2013 中設定語音信箱轉義](lync-server-2013-configuring-voice-mail-escape.md)  


[在 Lync Server 2013 中測試語音路由](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

