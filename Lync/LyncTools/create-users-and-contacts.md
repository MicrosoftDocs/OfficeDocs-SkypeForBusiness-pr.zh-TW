---
title: 建立使用者和連絡人
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Create Users and Contacts
ms:assetid: 04b24d07-2864-463d-b508-544c2674c4ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945587(v=OCS.15)
ms:contentKeyID: 51541412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f90e6cbb1afb9c4c2dd2b43e1448ca635899531b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-users-and-contacts"></a>建立使用者和連絡人

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

您必須使用 Lync Server 2013 使用者布建工具（UserProvisioningTool.exe）來建立使用者和連絡人，以準備壓力和效能負載測試。

以下是您在閱讀本主題時，可能會發現的術語和定義的清單。

  - 組織單位– Active Directory 網域服務組織單位（OU）。

  - 同盟/跨集區–啟用使用者與其他立即訊息（IM）服務（例如 Internet 服務的 MSN 網路、AOL®和 Yahoo®）進行通訊的使用者 \! 。

  - 通訊群組清單– Active Directory 網域服務中包含 Active Directory 網域服務使用者清單的物件，用來啟動與一組人員的通訊。

  - 位置資訊服務– Lync Server 2013 服務，啟用並設定每個電話時，可為增強9-1-1 （E9-1-1）服務，啟用實體位置的檢索。

  - 美國電話號碼–指派給使用者的電話號碼，除了用於路由輸入和撥出電話及反向號碼查閱（RNL）的 SIP URI 之外。

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>使用 UserProvisioningTool.exe 建立使用者和連絡人

您必須使用 Lync Server 使用者布建工具建立使用者和連絡人，以進行負載模擬。 Lync Server 使用者布建工具隨 Lync Server 壓力和效能工具套件一起安裝。 請確定已在前端伺服器或 Standard Edition server 上執行套件安裝程式（CapacityPlanningTool.msi）。 在 \\ 前端伺服器或 Standard Edition Server 上執行檔 UserProvisioningTool.exe （位於% InstalledDirectory% LyncStressAndPerfTool LyncStress），以啟動 Lync Server 使用者布建工具。

<div>


> [!IMPORTANT]  
> 您必須以 Domain Admins 安全性群組成員的身分登入，才能執行 UserProvisioningTool.exe。 您必須執行此內容，因為 UserProvisioningTool.exe 將會建立及設定新的 Active Directory 網域服務使用者。



</div>

<div>


> [!NOTE]  
> 當您建立大量的使用者（10000或更多）時，請從一部高端電腦執行 UserProvisioningTool.exe。 請注意，網域控制站也會在建立使用者時經歷高負載。



</div>

當 Lync Server 使用者布建工具開啟時，**按一下 [設定]，然後**選取 [**載入**設定]。 若要開始設定使用者和連絡人，請載入套件中所含的預設檔案 SampleData.xml。 這將會預設包含您的系統需要修訂之範例資料的欄位。 如果您有預先設定的 XML 檔案，而該檔案已包含自訂設定，請改為載入該檔案。 填寫 Lync Server 使用者布建工具中的欄位，如下列各節所述。

![[使用者建立] 索引標籤。](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "[使用者建立] 索引標籤。")

若要設定伺服器選項，請遵循下列步驟。

1.  在 [**前端集區 FQDN**] 中，輸入您要主控使用者之 Standard Edition Server 或前端集區的完整功能變數名稱（FQDN）。

2.  在 [**使用者名稱首碼**] 中，輸入您要用來建立用於測試目的之使用者名稱的前置詞。

3.  在 [**密碼**] 中，指定要套用於所有測試使用者帳戶的密碼。

4.  在 [ **SIP 網域**] 中，輸入要用於測試使用者之 SIP URIs 的功能變數名稱（統一資源識別項）。

5.  在 [**帳戶網域**] 中，輸入您目前 Active Directory 網域服務網域的功能變數名稱，您要在此網域中建立測試使用者。

6.  在 [**組織單位**] 中，輸入您要在其中建立使用者物件的 Active Directory 網域服務 OU 名稱。 如果 OU 不存在，則會建立該 OU。

7.  在 [**電話區號**] 中，輸入將用於測試使用者帳戶的三位數區功能變數代碼。 請確定電話區號不會與 Active Directory 網域服務中的任何其他使用者區功能變數代碼衝突。

8.  如果您想要啟用適用于 Enterprise Voice 的測試使用者，請選取 [**啟用語音功能**] 核取方塊。

9.  在 [**使用者數目**] 中，指定您要建立的測試使用者總數。

10. 在 [**起始索引**] 中，指定要用來做為使用者名稱前置詞尾碼的開始號碼。

<div>

## <a name="create-users-button"></a>建立使用者按鈕

當您按一下 [建立使用者] 按鈕時，它會驗證所有的輸入參數。

  - 如果有任何驗證錯誤，它會提示您修正輸入值。

  - 如果所有輸入值都是正確的，將會在 Active Directory 網域服務中開始建立使用者。 進度列會出現在此表單的底部。 建議您不要在進度列處於作用中時關閉應用程式。

使用者建立過程很慢。 可能需要幾分鐘的時間。 如果使用者數目非常大，則程式甚至可能需要數小時的時間。 如果使用者已存在，則會以任何變更更新。 您可以驗證使用者是否已以範圍中的其中一位使用者的身分登入來建立。 使用使用者前置詞、使用者號碼和 @sipDomain 做為使用者名稱（例如 LyncUser10@contoso.net），以及指定的密碼。

</div>

<div>

## <a name="delete-users-button"></a>[刪除使用者] 按鈕

當您按一下 [刪除使用者] 按鈕時，它會驗證所有的輸入參數。

  - 如果有任何驗證錯誤，它會提示您修正輸入值。

  - 如果所有輸入值都是正確的，將會開始停用或刪除 Active Directory 網域服務中的使用者。 進度列會出現在此表單的底部。 建議您不要在進度列處於作用中時關閉應用程式。

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P>只支援 U.S. 格式的電話號碼。 電話號碼一定會指派給使用者，而由 UserProvisioningTool.exe 所建立的所有使用者都是針對 Enterprise Voice 啟用。 使用電話號碼的任何案例（如會議自動語音應答或 UC-PSTN 通話）都會使用此電話號碼來正確地路由通話。 因此，每個使用者都必須有唯一的電話號碼。 如果您必須建立使用者兩次，除非您使用不同的區號，或是先前的使用者已使用<STRONG>get-csuser 指令程式</STRONG>停用，否則命令將會失敗。</P>
> <LI>
> <P>在您建立連絡人之前，必須先完成從 [使用者] 索引標籤執行的使用者複寫。如果您剛剛建立使用者，必須等到 Lync Server 複寫完成，並填入資料庫中的使用者帳戶。 如果使用者尚未完成複製，您會看到錯誤。 如果已啟動 Lync Server 2013 前端服務，或在最後一個使用者上成功執行<STRONG>Get-CsUser</STRONG> Cmdlet，您就會知道使用者何時完成複製。</P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a>[建立連絡人] 索引標籤

[連絡人建立] 索引標籤可讓您指定使用者連絡人的詳細資料。

![[建立連絡人] 索引標籤。](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "[建立連絡人] 索引標籤。")

若要設定使用者的連絡人，請遵循下列步驟。

1.  在 [每位使用者的平均連絡方式] 中，指定每位使用者的連絡人清單中所填入的連絡人平均人數。

2.  如果您想要為每位使用者建立相同數目的連絡人，請選取 [固定] 核取方塊。 如果您想要改變為使用者建立的連絡人數目，請清除此核取方塊。

3.  在 [每位使用者的平均連絡人群組] 中，指定每位使用者的連絡人群組數目。 此號碼必須小於每位使用者的平均連絡人數目。

4.  在 [同盟/跨集區連絡人百分比] 中，指定介於0到100之間的數位。 這則會以同盟使用者的連絡方式建立此百分比。

5.  在 [同盟/跨集區使用者前置詞] 中，指定將新增至本機使用者連絡人清單的同盟使用者的使用者名稱。

6.  在 [同盟/跨集區使用者 SIP 網域] 中，指定同盟使用者的 SIP 功能變數名稱。
    
    <div>
    

    > [!NOTE]  
    > 建立連絡人時，不應該登入任何使用者。

    
    </div>

7.  在 [使用者建立] 索引標籤中，確認參數是否正確。 在 [使用者建立] 索引標籤中，將建立連絡人的使用者範圍。

8.  按一下 [建立連絡人] 以開始建立連絡人。 此程式可能需要數分鐘的時間。 完成後，會出現一個對話方塊，其中會出現「作業已順利完成」的對話方塊。 您可以使用 [使用者建立] 索引標籤上所建立的使用者來驗證所建立的連絡人。
    
    <div>
    

    > [!NOTE]  
    > 建立連絡人之後，此工具將會重新開機目標集區中的所有前端伺服器。 前端伺服器可能需要較長時間（最多2小時）才能啟動，視此作業建立的連絡人數目而定。

    
    </div>

</div>

<div>

## <a name="distribution-list"></a>通訊群組清單

Lync Server 2013 壓力和效能工具的其中一項功能是模擬 Lync 2013 中的通訊群組清單（DL）擴充功能。 如果您不想要在 UserProvisioningTool 中啟用 DL 擴充，可以略過此步驟。

![[通訊群組清單建立] 索引標籤。](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "[通訊群組清單建立] 索引標籤。")

[通訊群組清單] 索引標籤可讓您建立壓力和效能工具將用於通訊群組清單擴充功能的 DLs。 在建立 DLs 之前，必須先安裝 Lync Server 2013。 您必須已執行 Lync Server 2013 ForestPrep。 否則，DL 屬性不存在於 Active Directory 網域服務架構中，而且工具將無法建立 DLs。

若要設定通訊群組清單，請遵循下列步驟。

1.  在 [通訊群組清單數目] 中，指定您要建立的 DLs 總數。 （建議您從使用者數目的兩倍開始）。 其編號為從0到 n-1。

2.  在 [通訊群組清單首碼] 中，指定 DLs 所擁有的前置詞。 例如，如果您指定 100 DLs 和首碼 testDL，則 DLs 會命名為 testDL0、testDL1 等等，而不是透過 testDL99。

3.  在 Dist 的 [最少成員] 清單中，指定每個通訊群組清單中要新增的使用者數目下限。

4.  在 [Dist] 中的 [最大成員] 清單中，指定每個通訊群組清單中要新增的使用者數目上限。

<div>

## <a name="create-distribution-lists-button"></a>建立通訊群組清單按鈕

當您按一下 [建立通訊群組清單] 按鈕時，此工具會查詢 Active Directory 網域服務，以查看符合首碼和號碼的通訊群組清單是否已存在。 工具只會建立尚未存在的專案。 將成員新增至這些新建立的通訊群組清單時，會從 [使用者建立] 索引標籤上指定的範圍內挑選使用者。

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a>位置資訊服務的 [配置] 索引標籤

Lync Server 2013 壓力和效能工具其中一項功能是針對位置資訊服務產生偽設定檔。 位置資訊服務通常對伺服器的效能沒有任何重大影響。

![[位置資訊服務 Config] 索引標籤。](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "[位置資訊服務 Config] 索引標籤。")

如果您選擇測試此功能，您可以填入表單中所述的值，然後按一下 [產生 .LIS 的 Config Files] 按鈕。 它會產生稱為 .LIS \_Subnet.csv、.lis \_Switches.csv、.Lis \_Ports.csv 和 .LISWAP.csv 的 CSV 檔案 \_ 。 然後，您可以將這些 CSV 檔案匯入到 .LIS 資料庫，方法是使用**CsLisSubnet**指令程式、 **CsLisSwitch**指令程式、set- **CsLisPort**指令程式，以及**設定 CsWirelessAccessPoint** Cmdlet。

</div>

</div>

<span> </span>

</div>

</div>

</div>

