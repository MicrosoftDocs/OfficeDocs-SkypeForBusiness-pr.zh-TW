---
title: 設定使用者設定檔
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure User Profile
ms:assetid: 52713245-e502-4539-a238-66ff1aca26b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945594(v=OCS.15)
ms:contentKeyID: 51541419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c53f156aee56aa1986302bf2ff2514aef78af592
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-user-profile"></a>設定使用者設定檔

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2018年-10-11_

包含在 Lync Server 2013 壓力及效能工具套件的工具可讓您建立及設定您可以使用來執行負載模擬的測試使用者帳戶。 使用 Lync Server 2013 使用者建立工具來建立的使用者。 （如需詳細資訊，請參閱[建立使用者和連絡人](create-users-and-contacts.md)）。建立使用者之後，請使用 Lync Server 2013 負載組態工具設定使用者設定檔。

<div>

## <a name="running-the-lync-server-2013-load-configuration-tool"></a>執行 Lync Server 2013 負載組態工具

若要設定使用者設定檔，請執行 Lync Server 2013 負載組態工具 (UserProfileGenerator.exe)，並填寫每個索引標籤。 UserProfileGenerator.exe 會為每個您要執行模擬用戶端電腦產生的目錄。 每個用戶端目錄也隨附的指令碼，以啟動的 [Lync Server 2013 壓力及效能工具 (LyncPerfTool.exe) 的所有執行個體。

<div>


> [!IMPORTANT]  
> UserProfileGenerator 中指定之特定使用者的值必須符合集區的 Lync Server 2013 使用者建立工具 (UserProvisioningTool) 中所指定的值。



</div>

下列各節所述，請填寫的 Lync Server 2013 負載組態工具，每個索引標籤上的欄位。

<div>

## <a name="common-configuration"></a>常見的設定

Lync Server 2013 負載組態工具的 [**通用設定**] 索引標籤下圖所示。 下列步驟所述填入 [**通用設定**] 索引標籤的欄位。

![一般設定] 索引標籤。](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "一般設定] 索引標籤。")

1.  在**可用機器數目**，輸入或按一下您要用以執行 LyncPerfTool.exe 的電腦數目。 我們建議您擁有的每個 4500 的使用者，您將會模擬一部電腦。 如果您降低負載層級，或如果您使用可用的功能的子集，該數字可能會有所不同。 （**一般案例**] 索引標籤上所設定的載入層級）。

2.  在 [**使用者名稱的前置字元**，輸入使用者的使用者名稱的前置詞。 若要登入，統一資源識別元 (URI) 將會是： UserPrefix\[使用者啟動索引...]（數字的使用者-1）\]@User 網域。

3.  在**所有使用者的密碼**] 中，輸入已用來建立使用者的密碼。 如果您將此欄位保留空白，將會用的使用者名稱的密碼。

4.  在**使用者開始的索引**中，按一下 [或輸入要設定第一位使用者的索引。 您可以設定不同範圍的不同類型或層級的負載，但您必須執行 UserProfileGenerator.exe 一次每個您想要設定的範圍。

5.  在 [**使用者數量**] 中，按一下 [或輸入您要設定的使用者總數。

6.  在**使用者網域**中，輸入用於 SIP URI 的網域。 這用來建構的 SIP URI，每一位使用者登入 Lync Server 2013 前端伺服器或 Standard Edition server。 它可以是不同的帳戶網域。

7.  在**帳戶網域**中，輸入登入 Active Directory 網域服務網域。

8.  在**登中每秒 （每個執行個體）** 您想要的工具來登入的所有端點/使用者輸入並行端點的最大數目。 建議的速率是\<= 每秒/標準 SKU FE 2。

9.  在**Access Proxy 或集區 FQDN]** 中，輸入您想用戶端連線至伺服器的完整的網域名稱 (FQDN)。 如果使用者從外部登入，指定 access proxy。 如果使用者是內部，指定其集區或 Standard Edition server 的 FQDN。

10. 在 [**連接埠**，按一下或輸入您想讓使用者使用的 SIP 連接埠 （預設值為 5061）。

針對外部網路伺服器設定]，指定的**Access Proxy 或集區 FQDN**和**連接埠**。 這些設定僅用於外部端點負載模擬。

</div>

<div>

## <a name="general-scenarios"></a>一般案例

Lync Server 2013 負載組態工具的 [**一般案例**] 索引標籤下圖所示。

設定每個您想要執行時，一般案例的載入層級和參數，或保留已停用。

![一般案例] 索引標籤。](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "一般案例] 索引標籤。")

1.  在**立即訊息**，其中包括對等和會議，指定負載層級適當的值。
    
    <div>
    

    > [!NOTE]  
    > 負載層級 （除了位置資訊服務） 的所有欄位都有效值為<STRONG>已停用</STRONG>、 <STRONG>Low</STRONG>、 <STRONG>Medium</STRONG>、<STRONG>高</STRONG>，及<STRONG>自訂</STRONG>。 選取低、 中、 高或自訂時，就會針對每種形式和用戶端產生組態。 高可能導致的最高的支援負載產生伺服器、 Medium 會對應至 60%的負載，及低會對應至 30%的負載。

    
    </div>

2.  **音訊會議**，也就是僅限音訊會議，在指定的載入層級適當的值。 對等通話涵蓋在本主題稍後的語音案例一節。 若要啟用 MultiView，開啟該模式下的 [**進階**] 索引標籤。

3.  在 [**應用程式共用**，指定的載入層級適當的值。

4.  在 [**資料共同作業**，其中包含資料會議，指定的載入層級適當的值。

5.  在 [**通訊群組清單擴充**，指定的載入層級適當的值。 您必須也按一下 [**進階**] 按鈕，然後填入您的 Lync Server 使用者建立工具 (UserProvisioningTool.exe) 的**通訊群組清單**] 索引標籤設定相同值的欄位。 如需這些欄位的詳細資訊，請參閱[建立使用者和連絡人](create-users-and-contacts.md)

6.  在 [**通訊錄 Web 查詢**，也就是通訊錄查閱服務 （不檔案下載通訊錄），指定的載入層級適當的值。 若要啟用通訊錄下載，請按一下對應的 [**進階**] 按鈕，然後將**EnableABSDownload**設為 true。

7.  在 [**回應群組服務**中，指定的載入層級適當的值。 您必須也按一下對應的 [**進階**] 按鈕，，，然後指定您已經建立佈建回應群組服務代理程式時的回應群組的 Uri。 您必須指定至少一個回應群組。 您可以使用分號分隔多個回應群組。 RGSUriSuffixStartIndex 和 RGSUriSuffixEndIndex 更新的實際值。

8.  **位置資訊服務**] 中選取適當的值的載入層級。 位置資訊服務的載入層級必須**已啟用**] 或 [**已停用**。

<div>


> [!NOTE]  
> 每個案例都位於，以及一組的核取方塊，啟用變化的案例旁邊的 [<STRONG>進階</STRONG>] 按鈕。 <STRONG>臨機操作</STRONG>表示要產生模擬的會議，將會建立整個小時。 <STRONG>大型 Conf</STRONG>表示將會模擬大型會議案例。 <STRONG>外部</STRONG>表示也模擬外部使用者。<BR>這些按鈕及核取方塊，允許存取值專屬於每個案例中，變更 [Lync Server 2013 壓力及效能工具 (LyncPerfTool) 的行為，並使自訂可能。 每個案例 （但不包括位置資訊服務） 的<STRONG>一般案例</STRONG>] 索引標籤上，如果負載層級的值是<STRONG>自訂</STRONG>]，然後交談率會進行計算在 [<STRONG>進階</STRONG>] 對話方塊中使用對應的欄位。 欄位名稱不同，根據案例，但將狀態欄位的描述，「 附註： 如果從下拉式清單功能表選取 [自訂，就只會使用此數字。 」 一般而言，<STRONG>高</STRONG>、<STRONG>中型</STRONG>與<STRONG>低</STRONG>的值會變更每種形式的所有案例的平衡使用者模型中內嵌的交談工資率。 如果沒有需要變更每種形式由於的差異在於預期的流量的負載層級，建議使用<STRONG>自訂</STRONG>交談工資率。<BR>



</div>

</div>

<div>

## <a name="voice-scenarios"></a>語音案例

Lync Server 2013 負載組態工具的 [**語音案例**] 索引標籤下圖所示。

使用 [**語音案例**] 索引標籤來設定的所有語音相關案例。

![語音案例] 索引標籤。](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "語音案例] 索引標籤。")

1.  在**VoIP**時，按一下 [**進階**] 按鈕，，然後提供 [ **PhoneAreaCode**和**LocationProfile** （撥號對應表）] 欄位的值。 您也必須指定值的**載入層級**。 如果已啟用**VoIP**和**UC/PSTN 閘道**的載入層級，然後就一定會產生公用交換的電話網路 (PSTN) 整合的通訊 (UC) 組態檔，將會模擬外部通話。

2.  **UC/PSTN 閘道**] 中指定的載入層級的值。 如果您選取的載入層級以外的**已停用**，您必須提供**PSTN 區域**代碼值中繼伺服器與 PSTN] 底下按一下 [**新增**] 按鈕。 確認您已設定該區域代碼的路由。
    
    <div>
    

    > [!NOTE]  
    > 若要確認語音路由組態，您可以使用 [Lync Server Control Panel] 或 [Lync Server 管理命令介面。

    
    </div>

3.  在 [**會議服務員**，指定的載入層級的值。 選取的載入層級 （以外的連接**已停用**)，將啟用 [**電話號碼**] 欄位。 輸入您想要使用自動語音應答的電話號碼。 此外，按一下 [**進階**] 按鈕，然後指定**LocationProfile**欄位的值。

4.  在 [**通話駐留服務**中，指定**的載入層級**適當的值。

5.  在**中繼伺服器和 PSTN**，每個中繼伺服器，您想要使用，您必須個別的 PSTN 模擬器。 您已決定您要做為模擬器用戶端之後，您需要在您設定的 PSTN 模擬器連接埠上設定中繼伺服器，以將通話路由傳送至該電腦。 按一下 [**新增]** 來為中繼伺服器設定的值。

<div>


> [!NOTE]  
> 每個案例都位於其旁邊的 [<STRONG>進階</STRONG>] 按鈕。 這些按鈕可讓每個案例中，變更 [Lync Server 2013 壓力及效能工具 (LyncPerfTool) 的行為，並啟用自訂的特定值的存取。 <STRONG>語音案例</STRONG>] 索引標籤上每個案例中，如果<STRONG>負載層級</STRONG>的值是<STRONG>自訂</STRONG>]，然後交談率會進行計算使用 [<STRONG>進階</STRONG>] 對話方塊中的對應的欄位。 欄位名稱不同，根據案例，但將狀態欄位的描述，「 附註： 如果從下拉式清單功能表選取 [自訂，就只會使用此數字。 」



</div>

</div>

<div>

## <a name="reach"></a>到達

範圍是支援透過前端伺服器安裝 Unified Communications Web API (UCWA) 伺服器的會議案例的 Lync Server 2013 中新的體驗。 Lync Server 2013 負載組態工具的 [**連線到**] 索引標籤下圖所示。

使用 [**連線到**] 索引標籤來設定所有範圍相關的案例。

![達到] 索引標籤。](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "達到] 索引標籤。")

1.  按一下 [**一般到達設定**] 旁的 [**進階**] 按鈕。 Set 功能變數**UcwaTargetServerUrl**至 Director 集區虛擬 IP (VIP) 或前端集區 VIP。

2.  在**應用程式共用**、**資料共同作業**，以及**IM**，選取適當的值的**載入層級**。

<div>


> [!NOTE]  
> 每個案例都位於其旁邊的 [<STRONG>進階</STRONG>] 按鈕。 這些按鈕可讓每個案例中，變更 [Lync Server 2013 壓力及效能工具 (LyncPerfTool) 的行為，並啟用自訂的特定值的存取。 針對每個範圍案例，如果<STRONG>負載層級</STRONG>是<STRONG>自訂</STRONG>]，然後<STRONG>ConversationsPerHour</STRONG>欄位中指定的值是用來取代預設值



</div>

若要設定的所有 mobility 相關案例中使用 [**行動性**] 索引標籤。

![行動性] 索引標籤。](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "行動性] 索引標籤。")

1.  按一下 [**進階**] 按鈕旁**行動力 (UCWA)**。 Set 功能變數**UcwaTargetServerUrl**至 Director 集區虛擬 IP (VIP) 或前端集區 VIP。

2.  在**Presence and P2P Instant Messaging\\音訊**，選取要啟用行動性案例模擬**的載入層級**適當的值。

<div>


> [!NOTE]  
> 每個案例都位於其旁邊的 [<STRONG>進階</STRONG>] 按鈕。 這些按鈕可讓每個案例中，變更 [Lync Server 2013 壓力及效能工具 (LyncPerfTool) 的行為，並啟用自訂的特定值的存取。 針對每個範圍案例中，如果<STRONG>負載層級</STRONG><STRONG>自訂</STRONG>]，然後<STRONG>ConversationsPerHour</STRONG>欄位中指定的值使用而不是預設值。



</div>

</div>

<div>

## <a name="summary"></a>摘要

Lync Server 2013 負載組態工具的 [**摘要**] 索引標籤下圖所示。

![摘要] 索引標籤。](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "摘要] 索引標籤。")

[**摘要**] 索引標籤會指出哪些使用者可使用每個案例。 它是可以手動設定使用者的號碼範圍依選取**啟用自訂使用者範圍產生**] 核取方塊，再連按兩下 [您想要自訂的**使用者範圍**的表格中的案例。 當啟動時，才能在對應的登入速度產生批次檔案中包含的延遲，請檢查 (RunClient.bat) 新增登入的延遲。 這很有用，避免伺服器超載時登入大量的使用者。 按一下 [**產生的檔案**，然後選取您想要用來產生組態的資料夾。 成功建立您的檔案時，會出現類似下列的圖] 對話方塊。

![檔案已建立的認可。](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "檔案已建立的認可。")

</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[建立使用者和連絡人](create-users-and-contacts.md)  
</div>
</div>
<span></span>
</div>
</div>
</div>
