---
title: 建立使用者和連絡人
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Create Users and Contacts
ms:assetid: 04b24d07-2864-463d-b508-544c2674c4ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945587(v=OCS.15)
ms:contentKeyID: 51541412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f09ac6fd667b77b47e27ec9fb9caac44b9a13e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-users-and-contacts"></a>建立使用者和連絡人

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

您必須使用 Lync Server 2013 使用者提供工具（UserProvisioningTool）來建立使用者和連絡人，才能準備壓力與效能負載測試。

以下是您在閱讀本主題時可能會發現的字詞和定義的清單。

  - 組織單位-Active Directory 網域服務組織單位（OU）。

  - [同盟/跨區]：可讓使用者從其他立即訊息（IM）服務（例如 MSN 網際網路服務、AOL®和® Yahoo\!）與使用者通訊的使用者。

  - 通訊群組清單： Active Directory 網域服務中包含 Active Directory 網域服務使用者清單的物件，用於啟動與人員群組的通訊。

  - 位置資訊服務-Lync Server 2013 服務（在每個手機上啟用和設定時）可讓您檢索增強9-1-1 （E9-1）服務的物理位置。

  - 美國電話號碼：指派給使用者的電話號碼，以及用於路由輸入和撥出通話與反向號碼查閱（RNL）的 SIP URI。

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>使用 UserProvisioningTool 建立使用者和連絡人

您必須使用 Lync Server 使用者預配工具來建立負載模擬的使用者和連絡人。 Lync server 使用者預配工具是隨 Lync Server 壓力和效能工具套件一起安裝。 請確定已在前端伺服器或標準版伺服器上執行套件安裝程式（CapacityPlanningTool）。 在前端伺服器或標準版伺服器上執行檔案 UserProvisioningTool （位於% InstalledDirectory% LyncStressAndPerfTool\\LyncStress），以啟動 Lync Server 使用者預配工具。

<div>


> [!IMPORTANT]  
> 您必須以網域管理員安全性群組的成員身分登入，才能執行 UserProvisioningTool。 您必須從這個內容執行，因為 UserProvisioningTool 會建立並設定新的 Active Directory 網域服務使用者。



</div>

<div>


> [!NOTE]  
> 當您建立有大量的使用者（10000或更多）時，請從高端電腦執行 UserProvisioningTool。 請注意，在建立使用者時，網網域控制站也會遇到高負載。



</div>

當 Lync Server 使用者提供工具開啟時 **，按一下 [設定]，然後**選取 [**載入**設定]。 若要開始配置使用者和連絡人，請載入套件中包含的預設檔案 SampleData .xml。 這將會針對您的系統所需修正的範例資料來預填入欄位。 如果您有預先配置的 XML 檔案，而該檔案已包含自訂的設定，請改為載入該檔案。 在 Lync Server 使用者預配工具中填入欄位，如下列各節所述。

[![使用者建立]]索引標籤。[(images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "使用者建立]")索引標籤。

若要設定伺服器選項，請遵循下列步驟。

1.  在 [**前端池 FQDN**] 中，輸入您要主持使用者之標準版伺服器或前端池的完整功能變數名稱（FQDN）。

2.  在 [**使用者名稱首碼**] 中，輸入您要用來建立使用者名稱以供測試之使用的首碼。

3.  在 [**密碼**] 中，指定將針對所有測試使用者帳戶套用的密碼。

4.  在**SIP 網域**中，輸入要用於測試使用者 sip Uri （統一資源識別項）的功能變數名稱。

5.  在 [**帳戶網域**] 中，輸入您目前 Active Directory 網域服務網域的功能變數名稱（您要在其中建立測試使用者）。

6.  在 [**組織單位**] 中，輸入您要在其中建立使用者物件之 Active Directory 網域服務組織單位的名稱。 如果 OU 不存在，就會建立它。

7.  在 [**電話區功能變數代碼**] 中，輸入要用於測試使用者帳戶的三位數區功能變數代碼。 請確定電話區代碼不會與 Active Directory 網域服務中其他使用者的區功能變數代碼發生衝突。

8.  如果您想要啟用企業語音測試使用者，請選取 [**已啟用語音**] 核取方塊。

9.  在 [**使用者數目**] 中，指定您要建立的測試使用者總數。

10. 在 [**起始索引**] 中，指定要用來做為使用者名稱首碼尾碼的起始數位。

<div>

## <a name="create-users-button"></a>[建立使用者] 按鈕

當您按一下 [建立使用者] 按鈕時，它會驗證所有輸入參數。

  - 如果有任何驗證錯誤，就會提示您修正輸入值。

  - 如果所有輸入值都是正確的，則會在 Active Directory 網域服務中開始建立使用者。 進度列會出現在此表單的底部。 我們建議您不要在進度列處於作用中時關閉應用程式。

使用者建立速度緩慢。 可能需要幾分鐘的時間。 如果使用者數量非常大，程式甚至可能需要幾個小時的時間。 如果使用者已經存在，則會使用任何變更進行更新。 您可以透過以範圍中的一位使用者的身分登入，來驗證使用者是否已建立。 使用使用者的前置詞、使用者編號及 @sipDomain 作為使用者名稱（例如，LyncUser10@contoso.net），以及指定的密碼。

</div>

<div>

## <a name="delete-users-button"></a>[刪除使用者] 按鈕

當您按一下 [刪除使用者] 按鈕時，它會驗證所有輸入參數。

  - 如果有任何驗證錯誤，就會提示您修正輸入值。

  - 如果所有輸入值都是正確的，就會開始停用並刪除 Active Directory 網域服務中的使用者。 進度列會出現在此表單的底部。 我們建議您不要在進度列處於作用中時關閉應用程式。

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P>僅支援美國格式的電話號碼。 電話號碼永遠會指派給使用者，而由 UserProvisioningTool 所建立的所有使用者都可以使用企業語音功能。 使用電話號碼（例如會議自動語音應答或 UC PSTN 通話）的任何案例，都可以使用此電話號碼來正確路由通話。 基於這個原因，每個使用者都必須有唯一的電話號碼。 如果您必須建立使用者兩次，除非您使用不同的區號，或使用<STRONG>Disable move-csuser</STRONG> Cmdlet 來停用先前的使用者，否則命令將會失敗。</P>
> <LI>
> <P>在您建立連絡人之前，您必須先完成從 [使用者] 索引標籤執行的使用者複製。如果您剛剛建立使用者，您必須等到 Lync Server 複製完成，然後填入資料庫中的使用者帳戶。 如果使用者尚未完成複製，您會看到錯誤。 如果 Lync Server 2013 前端服務已啟動，或在最後一個使用者上成功執行<STRONG>move-csuser</STRONG> Cmdlet，您就會知道使用者已完成複製的時間。</P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a>連絡人 [建立] 索引標籤

[連絡人建立] 索引標籤可讓您指定使用者連絡人的詳細資料。

![連絡人 [建立]]索引標籤。(images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "連絡人 [建立]")索引標籤。

若要設定使用者的連絡人，請執行下列步驟。

1.  在 [每位使用者平均連絡人] 中，指定要在連絡人清單中為每位使用者填入的連絡人平均數。

2.  如果您想要為每位使用者建立同等數量的連絡人，請選取 [固定] 核取方塊。 如果您想要變更為使用者建立的連絡人數目，請清除該核取方塊。

3.  在 [每位使用者的平均連絡人群組] 中，指定每位使用者的連絡人群組數量。 這個數位必須小於每位使用者的平均連絡人數。

4.  在 [聯盟/跨池連絡人百分比] 中，指定0到100之間的數位。 系統會使用聯盟使用者建立此連絡人的百分比。

5.  在 [同盟/跨池使用者首碼] 中，指定將新增至本機使用者連絡人清單的聯盟使用者的使用者名稱。

6.  在 [聯盟/跨池使用者 SIP 網域] 中，指定聯盟使用者的 SIP 功能變數名稱。
    
    <div>
    

    > [!NOTE]  
    > 無法在建立連絡人時登入任何使用者。

    
    </div>

7.  在 [使用者建立] 索引標籤中，確認參數正確無誤。 系統會從 [使用者建立] 索引標籤取得連絡人所要建立的使用者範圍。

8.  按一下 [建立連絡人]，開始建立連絡人。 這個程式可能需要幾分鐘的時間。 完成之後，會出現一個對話方塊，其中顯示 [作業已順利完成] 訊息。 您可以從以使用者 [建立] 索引標籤建立的使用者身分登入，以驗證所建立的連絡人。
    
    <div>
    

    > [!NOTE]  
    > 建立連絡人之後，此工具會重新開機目標池中的所有前端伺服器。 前端伺服器可能需要較長時間（最多2小時）才能啟動，視這個作業建立的連絡人數量而定。

    
    </div>

</div>

<div>

## <a name="distribution-list"></a>通訊群組清單

Lync Server 2013 應力和效能工具的其中一個功能，就是模擬 Lync 2013 中的通訊群組清單（DL）擴充功能。 如果您不打算在 UserProvisioningTool 中啟用 DL 延伸，您可以略過這個步驟。

[![通訊群組清單建立]]索引標籤。[(images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "通訊群組清單建立]")索引標籤。

[通訊群組清單] 索引標籤可讓您建立使用壓力與效能工具來進行通訊群組清單擴充功能的 Dl。 在建立 Dl 之前，必須先安裝 Lync Server 2013。 您必須已執行 Lync Server 2013 ForestPrep。 否則，DL 屬性不會存在於 Active Directory 網域服務架構中，且工具將無法建立 DLs。

若要設定通訊群組清單，請依照下列步驟進行。

1.  在 [通訊群組清單數目] 中，指定您要建立的 Dl 總數。 （我們建議您從兩個使用者數開始）。 它們的編號從0到 n-1。

2.  在通訊群組清單首碼中，指定 Dl 將擁有的前置詞。 例如，如果您指定 100 DLs 及 testDL 的首碼，系統會將 Dl 命名為 testDL0，testDL1，依此類推，直到 testDL99。

3.  在 [Dist] 中的 [最小成員] 清單中，指定要在每個通訊群組清單中新增的使用者數目。

4.  在 [Dist] 中的 [最大成員數] 清單中，指定要在每個通訊群組清單中新增的使用者數目上限。

<div>

## <a name="create-distribution-lists-button"></a>建立通訊群組清單按鈕

當您按一下 [建立通訊群組清單] 按鈕時，該工具會查詢 Active Directory 網域服務，以查看是否有符合該首碼和數位的通訊群組清單。 此工具只會建立尚不存在的專案。 將成員新增到這些新建立的通訊群組清單時，會從 [使用者建立] 索引標籤上指定的範圍中挑選使用者。

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a>位置資訊服務 [配置] 索引標籤

Lync Server 2013 應力和效能工具的其中一個功能，就是產生位置資訊服務的虛擬設定檔。 位置資訊服務通常不會對伺服器產生任何重要的效能影響。

![位置資訊服務 [配置]]索引標籤。(images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "位置資訊服務 [配置]")索引標籤。

如果您選擇要測試這項功能，您可以在表單中填入所提及的值，然後按一下 [產生 IIS 配置檔案] 按鈕。 它將會產生名為 .LIS\_子網 .CSV、.lis\_開關 .csv、.LIS\_埠 .csv 和 .lis\_的 WAP .csv 的 CSV 檔案。 接著，您可以使用**CsLisSubnet** Cmdlet、 **CsLisSwitch** Cmdlet、 **set CsLisPort** Cmdlet 以及**SET-CsWirelessAccessPoint** Cmdlet，將這些 CSV 檔案匯入到 iis 資料庫。

</div>

</div>

<span> </span>

</div>

</div>

</div>

