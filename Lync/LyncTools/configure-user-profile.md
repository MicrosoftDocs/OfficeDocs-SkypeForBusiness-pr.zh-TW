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
ms.openlocfilehash: a2441fe97bb57ffdf0f6200f1201e192bfc6bf14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-user-profile"></a>設定使用者設定檔

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2018-10-11_

Lync Server 2013 的 [應力] 和 [效能] 套件中所包含的工具可讓您建立並設定您可以用來執行負載模擬的測試使用者帳戶。 使用 Lync Server 2013 使用者建立工具來建立使用者。 （如需詳細資訊，請參閱[建立使用者和連絡人](create-users-and-contacts.md)。）建立使用者之後，請使用 Lync Server 2013 載入組態工具設定使用者設定檔。

<div>

## <a name="running-the-lync-server-2013-load-configuration-tool"></a>執行 Lync Server 2013 載入組態工具

若要設定使用者設定檔，請執行 Lync Server 2013 載入組態工具（UserProfileGenerator），然後填寫每個索引標籤。 UserProfileGenerator 會針對您需要執行模擬的每個用戶端電腦產生一個目錄。 每個用戶端目錄也隨附一個腳本來啟動 Lync Server 2013 應力和效能工具（LyncPerfTool）的所有實例。

<div>


> [!IMPORTANT]  
> 在 UserProfileGenerator 中指定的使用者特定值，必須符合在該池的 Lync Server 2013 使用者建立工具（UserProvisioningTool）中指定的值。



</div>

在 Lync Server 2013 載入組態工具的每個索引標籤上填入欄位，如下列各節所述。

<div>

## <a name="common-configuration"></a>常見配置

[Lync Server 2013 載入組態工具] 的 [**常用**設定] 索引標籤如下圖所示。 填寫 [**通用**設定] 索引標籤的欄位，如以下步驟所述。

![[Common Configuration] (一般設定) 索引標籤。](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "[Common Configuration] (一般設定) 索引標籤。")

1.  在 [**可用的電腦數**] 中，輸入或按一下您要用來執行 LyncPerfTool 的電腦數。 我們建議您針對您要模擬的每個4500使用者使用一部電腦。 如果您降低載入層級，或只使用可用功能的子集，該數位可能會有所不同。 （在 [**一般情況**] 索引標籤上設定 [負載等級]。）

2.  在 [**使用者名稱的前置**詞] 中，輸入使用者使用者名稱的首碼。 若要登入，統一資源識別項（URI）將會是：\[UserPrefix 使用者開始索引 .。。（使用者數目-1）\]@User 網域。

3.  在 [**所有使用者的密碼**] 中，輸入用來建立使用者的密碼。 如果您將此欄位保留空白，該使用者名稱將會用來做為密碼。

4.  在 [**使用者起始索引**] 中，按一下或輸入要設定的第一個使用者索引。 您可以針對不同的負載類型或等級設定不同的範圍，但您必須針對您想要設定的範圍執行 UserProfileGenerator 一次。

5.  在 [**使用者數目**] 中，按一下或輸入您要設定的使用者總數。

6.  在 [**使用者網域**] 中，輸入用於 SIP URI 的網域。 這是用來構造每個使用者的 SIP URI，以登入 Lync Server 2013 前端伺服器或標準版伺服器。 它可以與帳戶網域不同。

7.  在 [**帳戶網域**] 中，輸入 Active Directory 網域服務網域登入。

8.  輸入您想要讓該工具登入所有端點/使用者之**每秒（每個實例）** 的並行端點數目上限。 建議的工資率\<= 每秒 1/標準 SKU FE。

9.  在 [ **Access Proxy] 或 [池 FQDN**] 中，輸入您想要用戶端連線的伺服器的完整功能變數名稱（FQDN）。 如果使用者是在外部登入，請指定 [存取 proxy]。 如果使用者是 internal，請指定其池或標準版伺服器的 FQDN。

10. 在 [**埠**] 中，按一下或輸入您希望使用者用來使用 SIP 的埠（預設值為5061）。

針對外部網路伺服器設定，請指定**訪問 Proxy 或 POOL FQDN**和**埠**。 這些設定僅用於外部端點的負載模擬。

</div>

<div>

## <a name="general-scenarios"></a>一般案例

[Lync Server 2013 載入組態工具] 的 **[一般情況**] 索引標籤如下圖所示。

針對您要執行的每個一般案例，或 [保留停用] 來設定其負載等級與參數。

![[General Scenarios] (一般案例) 索引標籤。](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "[General Scenarios] (一般案例) 索引標籤。")

1.  在**立即訊息**（包括對等與會議）中，為載入層級指定適當的值。
    
    <div>
    

    > [!NOTE]  
    > 所有欄位的負載等級值（除了位置資訊服務）是<STRONG>停用</STRONG>、<STRONG>低</STRONG>、<STRONG>中</STRONG>、<STRONG>高</STRONG>，以及<STRONG>自訂</STRONG>。 選取 [低]、[中]、[高] 或 [自訂] 時，系統會針對每個模態與用戶端產生配置。 [高] 會導致為伺服器產生最大支援的載入，[中] 對應至60% 的負荷，而低則對應到負載的30%。

    
    </div>

2.  在**音訊**會議（僅適用于音訊會議）中，為載入層級指定適當的值。 對等通話會在本主題稍後的語音案例一節中講述。 若要啟用 [各頁]，請開啟該模態的 [**高級**] 索引標籤。

3.  在 [**應用程式共用**] 中，針對載入層級指定適當的值。

4.  在**資料**共同作業（包括資料會議）中，為載入層級指定適當的值。

5.  在**通訊群組清單展開**中，為載入層級指定適當的值。 您也必須按一下 [**高級**] 按鈕，然後使用您在 Lync Server 使用者建立工具（UserProvisioningTool）的 [**通訊群組清單**] 索引標籤上設定的值來填入欄位。 如需這些欄位的詳細資訊，請參閱[建立使用者和連絡人](create-users-and-contacts.md)

6.  在**通訊錄 Web 查詢**（這是通訊錄的查閱服務，而不是通訊錄檔案下載）中，為載入層級指定適當的值。 若要啟用通訊錄下載，請按一下對應的 [**高級**] 按鈕，然後將 [ **EnableABSDownload** ] 設定為 true。

7.  在 [**回應群組服務**] 中，為 [載入層級] 指定適當的值。 您也必須按一下對應的 [**高級**] 按鈕，然後指定您在預配回應群組服務代理程式時已建立之回應群組的 uri。 您必須指定至少一個回應群組。 使用分號來分隔多個回應群組。 將 RGSUriSuffixStartIndex 和 RGSUriSuffixEndIndex 更新為實際值。

8.  在 [**位置資訊服務**] 中，針對 [載入層級] 選取適當的值。 必須**啟用**或**停用**位置資訊服務的負載層級。

<div>


> [!NOTE]  
> 每個案例旁邊都有一個 [<STRONG>高級</STRONG>] 按鈕，以及一組可啟用案例變化的核取方塊。 <STRONG>特別是</STRONG>要產生將在一小時內建立的會議類比的方式。 <STRONG>大型</STRONG>會議代表將會模擬大型會議案例。 <STRONG>外部</STRONG>方式也是模擬外部使用者。<BR>這些按鈕和核取方塊可讓您存取每個案例所特有的值，這些值將會變更 Lync Server 2013 應力與效能工具（LyncPerfTool）的行為，並使得自訂功能成為可能。 針對 [<STRONG>一般案例</STRONG>] 索引標籤上的每個案例（[位置資訊服務] 除外），如果 [載入層級] 的值是 [<STRONG>自訂</STRONG>]，則會使用 [<STRONG>高級</STRONG>] 對話方塊中對應的欄位來計算交談比率。 欄位名稱會根據案例而有所不同，但欄位描述會是「注意：只有從下拉式功能表中選取 [自訂] 時，才會使用此號碼。」 一般來說，[<STRONG>高</STRONG>]、[<STRONG>中</STRONG>] 和 [<STRONG>低</STRONG>] 值會依與所有案例平衡的使用者模型來變更每個模態的交談比率。 如果由於預期使用量差異而需要變更每個模態的負載等級，建議您使用<STRONG>自訂</STRONG>交談速度。<BR>



</div>

</div>

<div>

## <a name="voice-scenarios"></a>語音案例

[Lync Server 2013 載入組態工具] 的 [**語音案例**] 索引標籤如下圖所示。

使用 [**語音案例**] 索引標籤來設定所有語音相關案例。

![[Voice Scenarios] (語音案例) 索引標籤。](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "[Voice Scenarios] (語音案例) 索引標籤。")

1.  在**VoIP**中，按一下 [**高級**] 按鈕，然後提供 [ **PhoneAreaCode** ] 和 [ **LocationProfile** （撥號方案）] 欄位的值。 您也必須為**載入層級**指定值。 如果已啟用 [ **VoIP**與**UC/PSTN 閘道**的負載等級]，就會一直產生將模擬外部呼叫的公用交換電話網絡（PSTN）設定檔。

2.  在 [ **UC/PSTN 閘道**] 中，指定 [負載等級] 的值。 如果您選取 [**停用**] 以外的載入層級，您必須在 [轉送伺服器和 PSTN] 底下，按一下 [**新增**] 按鈕，為**PSTN 區功能變數代碼**提供一個值。 確認您已針對該區功能變數代碼設定路由。
    
    <div>
    

    > [!NOTE]  
    > 您可以使用 Lync Server [控制台] 或 [Lync Server 管理命令介面] 來驗證語音路由設定。

    
    </div>

3.  在**會議助理**中，指定 [載入層級] 的值。 選取載入層級（除 [**停用**] 以外），即會啟用 [**電話號碼**] 欄位。 輸入您要使用之自動語音應答的電話號碼。 此外，按一下 [**高級**] 按鈕，然後指定 [ **LocationProfile** ] 欄位的值。

4.  在 [**通話駐留] 服務**中，為 [**載入層級**] 指定適當的值。

5.  在**轉送伺服器和 PSTN**中，針對您要使用的每個中繼伺服器，您必須有個別的 PSTN 模擬器。 確定您要用來做為模擬器的用戶端之後，您必須設定您的中繼伺服器，以將呼叫路由到您所設定的 PSTN 模擬器埠。 按一下 [**新增**] 以設定中繼伺服器的值。

<div>


> [!NOTE]  
> 每個案例旁邊都有一個 [<STRONG>高級</STRONG>] 按鈕。 這些按鈕可讓您存取會變更 Lync Server 2013 應力和效能工具（LyncPerfTool）行為並啟用自訂的每個案例特定的值。 針對 [<STRONG>語音案例</STRONG>] 索引標籤上的每個案例，如果 [<STRONG>載入層級</STRONG>] 的值是 [<STRONG>自訂</STRONG>]，則會使用 [<STRONG>高級</STRONG>] 對話方塊中對應的欄位來計算交談比率。 欄位名稱會根據案例而有所不同，但欄位描述會是「注意：只有從下拉式功能表中選取 [自訂] 時，才會使用此號碼。」



</div>

</div>

<div>

## <a name="reach"></a>接通

在 Lync Server 2013 中，[取得] 是一種新的體驗，可透過安裝在前端伺服器上的統一通訊 Web API （UCWA）伺服器來支援會議案例。 [Lync Server 2013 載入組態工具] 的 [**延伸**] 索引標籤如下圖所示。

使用 [**延伸**] 索引標籤來設定所有對等相關案例。

![[Reach] (連絡) 索引標籤。](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "[Reach] (連絡) 索引標籤。")

1.  按一下 **[一般延伸設定**] 旁的 [**高級**] 按鈕。 將 [欄位**UcwaTargetServerUrl** ] 設定為 [控制器池虛擬 IP （VIP）] 或 [頂層端池 VIP]。

2.  在 [**應用程式共用**]、[**資料**共同作業] 和 [ **IM**] 中，選取適當的**載入比例**值。

<div>


> [!NOTE]  
> 每個案例旁邊都有一個 [<STRONG>高級</STRONG>] 按鈕。 這些按鈕可讓您存取會變更 Lync Server 2013 應力和效能工具（LyncPerfTool）行為並啟用自訂的每個案例特定的值。 針對每個情形，如果<STRONG>載入層級</STRONG>是 [<STRONG>自訂</STRONG>]，則會使用 [ <STRONG>ConversationsPerHour</STRONG> ] 欄位中指定的值，而不是預設值



</div>

使用 [**行動**] 索引標籤來設定所有行動相關案例。

![[Mobility] (行動) 索引標籤。](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "[Mobility] (行動) 索引標籤。")

1.  按一下 [**行動性（UCWA）**] 旁的 [**高級**] 按鈕。 將 [欄位**UcwaTargetServerUrl** ] 設定為 [控制器池虛擬 IP （VIP）] 或 [頂層端池 VIP]。

2.  在目前**狀態與 P2P 立即\\訊息音訊**中，選取適當的**負載層級**值，以啟用行動案例模擬。

<div>


> [!NOTE]  
> 每個案例旁邊都有一個 [<STRONG>高級</STRONG>] 按鈕。 這些按鈕可讓您存取會變更 Lync Server 2013 應力和效能工具（LyncPerfTool）行為並啟用自訂的每個案例特定的值。 針對每個延伸案例，如果<STRONG>載入層級</STRONG>為 [<STRONG>自訂</STRONG>]，則會使用 [ <STRONG>ConversationsPerHour</STRONG> ] 欄位中指定的值，而不是預設值。



</div>

</div>

<div>

## <a name="summary"></a>總結

[Lync Server 2013 載入組態工具] 的 [**摘要**] 索引標籤如下圖所示。

![[Summary] (摘要) 索引標籤。](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "[Summary] (摘要) 索引標籤。")

[**摘要**] 索引標籤會指出要在每個案例中使用的使用者。 若要手動設定使用者編號範圍，請選取 [**啟用自訂使用者範圍產生**] 核取方塊，然後在包含您要自訂之**使用者範圍**的資料表中，按兩下該案例。 Check （RunClient）在啟動時加入登入延遲，以包含產生的批次檔案中的延遲，以與登入速率相對應。 在登入大量的使用者時，這對避免伺服器超載很有用。 按一下 [**產生**檔案]，然後選取您要產生配置的資料夾。 當您的檔案已成功建立之後，就會出現類似下圖的對話方塊。

![檔案已建立的確認通知。](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "檔案已建立的確認通知。")

</div>

</div>

<div>

## <a name="see-also"></a>請參閱


[建立使用者和連絡人](create-users-and-contacts.md)  
</div>
</div>
<span></span>
</div>
</div>
</div>
