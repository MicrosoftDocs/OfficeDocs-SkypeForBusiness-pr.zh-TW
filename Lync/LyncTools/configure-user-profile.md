---
title: 設定使用者設定檔
description: 設定使用者設定檔。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure User Profile
ms:assetid: 52713245-e502-4539-a238-66ff1aca26b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945594(v=OCS.15)
ms:contentKeyID: 51541419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 682297da43797dd2d774094e85e8688ef3c64d98
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573089"
---
# <a name="configure-user-profile"></a>設定使用者設定檔

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2018-10-11_

Lync Server 2013 應力和效能工具套件所包含的工具可讓您建立及設定測試使用者帳戶，以供您用來執行負載模擬。 使用 Lync Server 2013 使用者建立工具來建立使用者。  (如需詳細資訊，請參閱 [建立使用者和連絡人](create-users-and-contacts.md)。 ) 建立使用者之後，使用 Lync Server 2013 負載設定工具設定使用者設定檔。

<div>

## <a name="running-the-lync-server-2013-load-configuration-tool"></a>執行 Lync Server 2013 載入設定工具

若要設定使用者設定檔，請執行 Lync Server 2013 載入設定工具 ( # A0) 並填妥每個索引標籤。 UserProfileGenerator.exe 會為您需要執行模擬的每一部用戶端電腦產生目錄。 每個用戶端目錄也附帶一個腳本，以啟動 Lync Server 2013 應力和效能工具 ( # A0) 的所有實例。

<div>


> [!IMPORTANT]  
> Userprofilegenerator.exe 中指定的使用者特定值，必須符合 Lync Server 2013 使用者建立工具中所指定的值，才能 (集區的 UserProvisioningTool) 。



</div>

在 [Lync Server 2013 載入設定工具] 的每個索引標籤上填入欄位，如下列各節所述。

<div>

## <a name="common-configuration"></a>一般設定

下圖顯示 Lync Server 2013 Load Configuration 工具的 [ **一般** 設定] 索引標籤。 填寫 [ **一般** 設定] 索引標籤的欄位，如下列步驟所述。

![通用設定] 索引標籤。](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "通用設定] 索引標籤。")

1.  在 [ **可用機器數目**] 中，輸入或按一下您要用來執行 LyncPerfTool.exe 的電腦數目。 建議您為每個要模擬的4500使用者提供一部電腦。 如果您降低負載層級，或僅使用可用功能的子集，該數位可能會有所不同。  (負載層級是在 [ **一般案例** ] 索引標籤上設定。 ) 

2.  在 [ **使用者名稱的前置**詞] 中，輸入使用者之使用者名稱的前置詞。 若要登入，統一資源識別項 (URI) 會是： UserPrefix \[ User Start Index ... (使用者數目-1) \] @User Domain。

3.  在 [ **所有使用者的密碼**] 中，輸入用來建立使用者的密碼。 如果您將此欄位保留空白，則會將使用者名稱當作密碼使用。

4.  在 [ **使用者起始索引**] 中，按一下或輸入要設定之第一個使用者的索引。 您可以為不同的類型或不同的負載層級設定不同的範圍，但是必須針對您要設定的範圍執行 UserProfileGenerator.exe 一次。

5.  在 [ **使用者數目**] 中，按一下或輸入您要設定的使用者總數。

6.  在 [ **使用者網域**] 中，輸入用於 SIP URI 的網域。 這是用來建立每一位使用者的 SIP URI，以登入 Lync Server 2013 前端伺服器或 Standard Edition server。 它可以不同于帳戶網域。

7.  在 [ **帳戶網域**] 中，輸入 Active Directory 網域服務網域登入。

8.  輸入您想要讓工具在所有端點/使用者中登入的每 **秒以每秒 (每個實例) ** 的並行端點數目上限。 建議的速率為 \< = 每秒 2/STANDARD SKU FE。

9.  在 [ **Access Proxy 或集區 FQDN**] 中，輸入您要讓用戶端連接之伺服器的完整功能變數名稱 (FQDN) 。 若使用者在外部登入，請指定 access proxy。 如果使用者是內部使用者，請指定其集區或 Standard Edition server 的 FQDN。

10. 在 [ **埠**] 中，按一下或輸入您想要讓使用者用於 SIP 的埠 (預設值為 5061) 。

針對 [外部網路伺服器設定]，指定 **Access Proxy 或集區 FQDN** 和 **埠**。 這些設定只用于外部端點的負載模擬。

</div>

<div>

## <a name="general-scenarios"></a>一般案例

[Lync Server 2013 載入設定工具] 的 **[一般案例** ] 索引標籤如下圖所示。

針對您想要執行的每個一般案例，設定負載層級和參數，或停用停用。

![一般案例] 索引標籤。](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "一般案例] 索引標籤。")

1.  在 **立即訊息**中（包括對等和會議），為負載層級指定適當的值。
    
    <div>
    

    > [!NOTE]  
    > 所有欄位的負載層級值 (，但位置資訊服務) 會 <STRONG>停用</STRONG>、 <STRONG>低</STRONG>、 <STRONG>中</STRONG>、 <STRONG>高</STRONG>及 <STRONG>自訂</STRONG>。 選取 [低]、[中]、[高] 或 [自訂] 時，將會針對每個模態和用戶端產生設定。 High 會產生為伺服器產生的最大支援負載，中會對應至60% 的負載，低的負載會對應至30% 的負載。

    
    </div>

2.  在 [ **音訊會議**] （僅限音訊會議）中，為 [負載層級] 指定適當的值。 對等通話會在本主題稍後的語音案例區段中講述。 若要啟用所有的查看，請開啟該形式的 [ **高級** ] 索引標籤。

3.  在 [ **應用程式共用**] 中，為 [負載層級] 指定適當的值。

4.  在 [ **資料**共同作業] （包含資料會議）中，為 [負載層級] 指定適當的值。

5.  在 [ **通訊群組清單展開**] 中，為 [負載層級] 指定適當的值。 您也必須按一下 [ **高級** ] 按鈕，然後以 Lync Server 使用者建立工具 ( # A0) 中的 [ **通訊群組清單** ] 索引標籤上所設定的相同值填入欄位。 如需這些欄位的詳細資訊，請參閱 [建立使用者和連絡人](create-users-and-contacts.md)

6.  在 [通訊 **簿 Web 查詢**] 中，這是通訊錄的查閱服務 (不是通訊錄檔案下載) ，請為 [負載層級] 指定適當的值。 若要啟用通訊錄下載，請按一下對應的 [ **高級** ] 按鈕，然後將 **EnableABSDownload** 設定為 true。

7.  在 [ **回應群組服務**] 中，指定適當的負載層級值。 您也必須按一下對應的 [ **高級** ] 按鈕，然後指定在布建回應群組服務代理程式時，您已建立的回應群組 URIs。 您必須指定至少一個回應群組。 使用分號分隔多個回應群組。 將 RGSUriSuffixStartIndex 及 RGSUriSuffixEndIndex 更新為實際值。

8.  在 [ **位置資訊服務**] 中，選取適當的負載層級值。 必須 **啟用** 或 **停用**位置資訊服務的負載層級。

<div>


> [!NOTE]  
> 每個案例旁都有一個「 <STRONG>高級</STRONG> 」按鈕，以及一組啟用案例變化的核取方塊。 <STRONG>特別表示要</STRONG> 產生一小時內建立的會議類比。 「<STRONG>大型</STRONG>會議」表示將會模擬大型會議案例。 <STRONG>外部</STRONG> 方式也可模擬外部使用者。<BR>這些按鈕和核取方塊可讓您存取每個案例特有的值，這些值會變更 Lync Server 2013 壓力和效能工具 (LyncPerfTool) 的行為，並可進行自訂。 針對 [ <STRONG>一般案例</STRONG> ] 索引標籤上的每個案例 (除位置資訊服務) 之外，如果負載層級的值是 [ <STRONG>自訂</STRONG>]，就會使用 [ <STRONG>高級</STRONG> ] 對話方塊中對應的欄位來計算交談率。 功能變數名稱會不同，具體取決於案例，但是欄位描述將會是「注意：只有從下拉式功能表中選取 [自訂] 時，才會使用此號碼。 一般說來， <STRONG>高</STRONG>、 <STRONG>中</STRONG>、 <STRONG>低</STRONG> 的值將會以所有案例的平衡的使用者模型來變更每個形式的交談比率。 如果因預期的使用量差異而需要變更每個模態的負載層級，建議使用 <STRONG>自訂</STRONG> 交談率。<BR>



</div>

</div>

<div>

## <a name="voice-scenarios"></a>語音案例

[Lync Server 2013 載入設定工具] 的 [ **語音案例** ] 索引標籤如下圖所示。

使用 [ **語音案例** ] 索引標籤來設定所有語音相關案例。

![語音案例] 索引標籤。](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "語音案例] 索引標籤。")

1.  在 **VoIP**中，按一下 [ **高級** ] 按鈕，然後提供 **PhoneAreaCode** 和 **microsoft.rtc.management.writableconfig.policy.voice.locationprofile** (撥號對應表) ] 欄位的值。 您也必須指定 **負載層級**的值。 如果啟用 **VoIP** 和 **UC/PSTN 閘道** 的負載層級，則會永遠會產生一部公用交換電話網路 (PSTN) 至整合通訊 (UC) 設定檔，以模擬外部通話。

2.  在 [ **UC/PSTN 閘道**] 中，為 [負載層級] 指定一個值。 如果您選取**停用**以外的載入層級，您必須按一下 [轉送伺服器和 PSTN] 底下的 [**新增**] 按鈕，為**PSTN 區域碼**提供值。 請確認您是否已為該區號設定路由。
    
    <div>
    

    > [!NOTE]  
    > 您可以使用 Lync Server 控制台或 Lync Server 管理命令介面來驗證語音路由設定。

    
    </div>

3.  在 **會議助理**中，指定負載層級的值。 選取除 **停用**) 以外的負載層級 (會啟用 [ **電話號碼** ] 欄位。 輸入您要使用之自動語音應答的電話號碼。 此外，按一下 [ **高級** ] 按鈕，然後指定 [ **microsoft.rtc.management.writableconfig.policy.voice.locationprofile** ] 欄位的值。

4.  在 [ **通話駐留服務**] 中，為 [ **負載層級**] 指定適當的值。

5.  在中繼 **伺服器和 PSTN**中，針對您想要使用的每個轉送伺服器，您必須有個別的 PSTN 模擬器。 決定要用來做為模擬器的用戶端後，您需要將您的轉送伺服器設定為在您設定的 PSTN 模擬器埠上，將通話路由傳送至該電腦。 按一下 [ **新增** ] 以設定轉送伺服器的值。

<div>


> [!NOTE]  
> 每個案例都有一個位於它旁邊的 [ <STRONG>高級</STRONG> ] 按鈕。 這些按鈕允許存取每個案例特有的值，這些值會變更 Lync Server 2013 壓力和效能工具 (LyncPerfTool) 並啟用自訂的行為。 在 [ <STRONG>語音案例</STRONG> ] 索引標籤上的每個案例中，如果 [ <STRONG>負載層級</STRONG> ] 的值為 [ <STRONG>自訂</STRONG>]，則會使用 [ <STRONG>高級</STRONG> ] 對話方塊中對應的欄位來計算交談率。 功能變數名稱會不同，具體取決於案例，但是欄位描述將會是「注意：只有從下拉式功能表中選取 [自訂] 時，才會使用此號碼。



</div>

</div>

<div>

## <a name="reach"></a>達到

「接觸」是 Lync Server 2013 中的新經驗，可透過 Front-End Server 上安裝的整合通訊 Web API (UCWA) 伺服器來支援會議案例。 下圖顯示 Lync Server 2013 負載設定工具的 [ **範圍** ] 索引標籤。

使用 [ **範圍** ] 索引標籤來設定所有與範圍相關的案例。

![[接觸] 索引標籤。](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "[接觸] 索引標籤。")

1.  按一下 [**一般到達設定**] 旁的 [**高級**] 按鈕。 將欄位 **UcwaTargetServerUrl** 為 Director 集區虛擬 IP (VIP) 或前端集區 VIP。

2.  在 [ **應用程式共用**]、[ **資料**共同作業] 和 [ **IM**] 中，選取適當的 **負載層級**值。

<div>


> [!NOTE]  
> 每個案例都有一個位於它旁邊的 [ <STRONG>高級</STRONG> ] 按鈕。 這些按鈕允許存取每個案例特有的值，這些值會變更 Lync Server 2013 壓力和效能工具 (LyncPerfTool) 並啟用自訂的行為。 針對每個接觸案例，如果 <STRONG>負載層級</STRONG> 為 [ <STRONG>自訂</STRONG>]，則使用 <STRONG>ConversationsPerHour</STRONG> 欄位中指定的值，而不是預設值



</div>

使用 [ **行動性** ] 索引標籤來設定所有行動相關案例。

![行動] 索引標籤。](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "行動] 索引標籤。")

1.  按一下 [**行動性 (UCWA) **旁的 [**高級**] 按鈕。 將欄位 **UcwaTargetServerUrl** 為 Director 集區虛擬 IP (VIP) 或前端集區 VIP。

2.  在 [ **顯示並 P2P 立即訊息 \\ 音訊**] 中，選取適當的 **負載層級** 值，以啟用行動案例類比。

<div>


> [!NOTE]  
> 每個案例都有一個位於它旁邊的 [ <STRONG>高級</STRONG> ] 按鈕。 這些按鈕允許存取每個案例特有的值，這些值會變更 Lync Server 2013 壓力和效能工具 (LyncPerfTool) 並啟用自訂的行為。 針對每個接觸案例，如果 <STRONG>負載層級</STRONG> 為 [ <STRONG>自訂</STRONG>]，則使用 <STRONG>ConversationsPerHour</STRONG> 欄位中指定的值，而不是預設值。



</div>

</div>

<div>

## <a name="summary"></a>摘要

下圖顯示 Lync Server 2013 Load Configuration 工具的 [ **摘要** ] 索引標籤。

![摘要] 索引標籤。](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "摘要] 索引標籤。")

[ **摘要** ] 索引標籤會指出要針對每個案例使用的使用者。 您可以手動設定使用者號碼範圍，方法是選取 [ **啟用自訂使用者範圍產生** ] 核取方塊，然後在具有您要自訂之 **使用者範圍** 的資料表中按兩下案例。 檢查 ( # A0) 在啟動時加入登入延遲，以便在產生的批次處理檔案中包含延遲，以對應于登入率。 當您簽署大量使用者時，這是避免伺服器超載的有用方法。 按一下 [ **產生**檔案]，然後選取您要產生設定的資料夾。 當您已成功建立檔案時，就會出現類似下圖的對話方塊。

![確認已建立檔案。](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "確認已建立檔案。")

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
