---
title: 建立使用者和連絡人
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Create Users and Contacts
ms:assetid: 04b24d07-2864-463d-b508-544c2674c4ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945587(v=OCS.15)
ms:contentKeyID: 51541412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 660ac18e00ef25a3cda4dd37d6a7850fee2fa459
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-users-and-contacts"></a>建立使用者和連絡人

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-22_

您必須使用 Lync Server 2013 使用者佈建工具 (UserProvisioningTool.exe) 來建立使用者和連絡人以準備壓力及效能負載測試。

以下是可能有幫助您閱讀透過本主題的詞彙與定義的清單。

  - 組織單位 – Active Directory 網域服務組織單位 (OU)。

  - 同盟 / 跨集區-會啟用的使用者從其他立即訊息 (IM) 服務，例如網際網路服務、 AOL®，和 Yahoo MSN 網路進行通訊的使用者\!®。

  - 通訊群組清單 – 包含 Active Directory 網域服務使用者，用來啟動與組群的人通訊清單的 Active Directory 網域服務中的物件。

  - 位置資訊服務 – 可時啟用及設定每個電話，讓您擷取增強型 9-1-1 (E9-1-1) 服務的實體位置的 Lync Server 2013 服務。

  - 美國電話號碼 – 指派給使用者，除了用於路由內送和外送呼叫的 SIP URI 和反向號碼查閱 (RNL) 的電話號碼。

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>使用 UserProvisioningTool.exe 建立使用者和連絡人

您必須使用 Lync Server 使用者佈建工具來建立使用者和連絡人負載模擬。 使用 Lync Server 壓力及效能工具套件安裝 Lync Server 使用者佈建工具。 請確定已在前端伺服器或 Standard Edition server 上執行套件安裝程式 (CapacityPlanningTool.msi)。 啟動 Lync Server 使用者佈建工具執行檔案 UserProvisioningTool.exe (位於 %installeddirectory%LyncStressAndPerfTool\\LyncStress) Standard Edition server 或前端伺服器上。

<div>


> [!IMPORTANT]  
> 您必須登入以 Domain Admins 安全性群組的成員才能執行 UserProvisioningTool.exe。 就必須執行從這個內容，因為 UserProvisioningTool.exe 會建立及設定新的 Active Directory 網域服務使用者。



</div>

<div>


> [!NOTE]  
> 當您建立大量的使用者 （10000 或多個） 時，請從高階電腦執行 UserProvisioningTool.exe。 請注意的網域控制站會也遇到高的負載時正在建立的使用者。



</div>

為 Lync Server 使用者佈建工具開啟時，按一下 [**組態**]，然後選取 [**載入組態**。 若要開始設定使用者和連絡人，載入封裝，SampleData.xml 中包含的預設檔案。 這會預先填入範例資料，您需要為您的系統修訂的欄位。 如果您有預先設定的 XML 檔案，其中已包含自訂的設定，請改為載入該檔案。 下列各節所述的欄位中為 Lync Server 使用者佈建工具，填滿。

![使用者建立] 索引標籤。](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "使用者建立] 索引標籤。")

若要設定伺服器選項，請遵循下列步驟。

1.  在**前端集區 FQDN**] 中，輸入 Standard Edition server 或您想要用來主控使用者的前端集區的完整的網域名稱 (FQDN)。

2.  在 [**使用者名稱前置詞**，輸入您想要用來建立用於測試的使用者名稱的前置詞。

3.  在 [**密碼**] 中，指定將套用的所有測試使用者帳戶的密碼。

4.  在**SIP 網域**中，輸入要用於測試使用者的 SIP Uri （統一資源識別元） 的網域名稱。

5.  在 [**帳戶網域**中，輸入您目前的 Active Directory 網域服務網域，您想要建立測試使用者所屬的網域名稱。

6.  在 [**組織單位**中，輸入您想要用來建立使用者物件 Active Directory 網域服務 OU 的名稱。 如果 OU 不存在，則會加以建立。

7.  在 [**電話] 區域的程式碼**中，輸入將用於測試使用者帳戶的三位數區域程式碼。 請確定該電話區碼不要與任何其他使用者的 Active Directory 網域服務中的區域代碼衝突。

8.  如果您想要測試為使用者啟用 Enterprise Voice，請選取 [**語音**] 核取方塊。

9.  在 [**使用者數量**，指定您想要建立的測試使用者的總數。

10. 在**開始的索引**中，指定要作為尾碼的使用者名稱前置詞的起始編號。

<div>

## <a name="create-users-button"></a>建立使用者] 按鈕

當您按一下 [建立的使用者] 按鈕時，會驗證所有輸入的參數。

  - 如果有任何驗證錯誤，它會提示您若要修正這些輸入的值。

  - 如果所有輸入的值是否正確，則會啟動 Active Directory 網域服務中建立使用者。 進度列會出現在此表單的底部。 我們建議您不要關閉應用程式，當進度列作用中。

使用者建立是緩慢的程序。 可能需要幾分鐘的時間。 如果使用者數目很大，處理程序甚至可能需要幾個小時。 如果使用者已存在，他們會更新的任何變更。 您可以驗證由以下列其中一個範圍中的使用者登入已建立的使用者。 使用使用者的前置詞、 使用者數目和 @sipDomain 作為使用者名稱 (例如，LyncUser10@contoso.net)，以及指定的密碼。

</div>

<div>

## <a name="delete-users-button"></a>刪除使用者] 按鈕

當您按一下刪除使用者] 按鈕上時，會驗證所有輸入的參數。

  - 如果有任何驗證錯誤，它會提示您若要修正這些輸入的值。

  - 如果所有輸入的值是否正確，則會啟動停用和刪除 Active Directory 網域服務中的使用者。 進度列會出現在此表單的底部。 我們建議您不要關閉應用程式，當進度列作用中。

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P>支援僅限美國格式的電話號碼。 電話號碼一律會指派給使用者，以及 UserProvisioningTool.exe 所建立的所有使用者都啟用 Enterprise voice。 任何使用的電話號碼，例如會議自動語音應答或 UC-PSTN 通話的案例使用此電話號碼正確地路由傳送來電。 基於這個理由，每一位使用者必須有唯一的電話號碼。 如果您有兩次建立使用者，命令將會失敗，除非您使用不同的區碼，或已停用舊的使用者使用<STRONG>Disable-csuser</STRONG> cmdlet。</P>
> <LI>
> <P>建立連絡人之前，您必須先完成使用者複製，執行 [使用者] 索引標籤。如果您剛建立您的使用者，您必須等到 Lync Server 複寫完成，並填入資料庫中的使用者帳戶。 如果使用者尚未完成複寫，您會看到錯誤。 您會知道當使用者完成複寫如果 Lync Server 2013 前端服務已啟動，或藉由成功，最後一個使用者執行<STRONG>Get-csuser</STRONG> cmdlet。</P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a>連絡人建立] 索引標籤

[連絡人建立] 索引標籤可讓您指定的使用者的連絡人詳細資料。

![連絡人建立] 索引標籤。](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "連絡人建立] 索引標籤。")

若要設定使用者的連絡人，請遵循下列步驟。

1.  在每位使用者的平均連絡人，指定要填入連絡人清單中的每位使用者的連絡人的平均數目。

2.  如果您想要建立數等於相同數目的每一位使用者的連絡人，請選取 [固定的核取方塊。 如果您想要為使用者所建立的連絡人數目而異，清除此核取方塊。

3.  平均連絡人群組中每位使用者，指定每位使用者的連絡人群組的數目。 此數字必須小於每位使用者的平均連絡人。

4.  在 [同盟 / 跨集區連絡人百分比，指定介於 0 到 100 之間的數字。 此百分比的連絡人會建立與同盟使用者。

5.  在 [同盟 / 跨集區使用者前置詞，指定將會新增到本機使用者的連絡人清單的同盟使用者的使用者名稱。

6.  在 [同盟 / 跨集區的使用者 SIP 網域，請指定同盟使用者的 SIP 網域名稱。
    
    <div>
    

    > [!NOTE]  
    > 使用者都應該登入，當建立連絡人。

    
    </div>

7.  在使用者建立] 索引標籤，確認參數正確無誤。 使用者將會為其建立連絡人的範圍被取自使用者建立] 索引標籤。

8.  按一下 [開始連絡人建立建立連絡人。 此程序可能需要幾分鐘。 它完成時，郵件時，會出現對話方塊之後 「 作業成功完成。 」 您可以驗證由使用者建立] 索引標籤所建立的使用者身分登入所建立的連絡人。
    
    <div>
    

    > [!NOTE]  
    > 建立連絡人之後，此工具會目標集區中重新啟動所有前端伺服器。 根據多少連絡人所建立的這項作業可能需要較長 （最多 2 小時） 的開始，前端伺服器。

    
    </div>

</div>

<div>

## <a name="distribution-list"></a>通訊群組清單

其中一項功能的 [Lync Server 2013 壓力及效能工具會模擬 Lync 2013 中的通訊清單 (DL) 的擴充功能。 如果您不能在 UserProvisioningTool DL 擴充，您可以略過此步驟。

![通訊群組清單的建立] 索引標籤。](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "通訊群組清單的建立] 索引標籤。")

[通訊群組清單] 索引標籤可讓您建立的壓力及效能工具，將會用於通訊群組清單擴充功能的通訊群組清單。 之前建立通訊群組清單，必須已安裝 Lync Server 2013。 您必須執行 Lync Server 2013 ForestPrep。 否則，DL 屬性不存在於 Active Directory 網域服務架構，此工具不能建立通訊群組清單。

若要設定通訊群組清單，請遵循下列步驟。

1.  在 [數字的通訊群組清單，指定您想要建立的通訊群組清單的總數。 （建議使用開始的兩倍的使用者數目）。 他們是從 0 到編號 n-1。

2.  在 [通訊群組清單的前置詞，指定通訊群組清單會有前置詞。 例如 testDL0、 testDL1，等等，透過 testDL99，如果您指定 100 Dl 和 testDL 的前置詞，將名為通訊群組清單。

3.  在最小 Dist.清單中的成員，指定要在每個通訊群組清單中新增使用者的數下限。

4.  在 [Dist.] 清單中的最大成員，指定要在每個通訊群組清單中新增使用者的數目上限。

<div>

## <a name="create-distribution-lists-button"></a>建立通訊群組清單] 按鈕

當您按一下 [建立通訊群組清單] 按鈕時，工具會查詢 Active Directory 網域服務，以查看是否通訊群組清單比對的首碼和號碼已經存在。 此工具會建立不存在的探索。 當將成員新增至新建立的通訊群組清單，它會選擇將使用者從使用者建立] 索引標籤上指定的範圍。

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a>位置資訊服務設定] 索引標籤

下列其中一個 [Lync Server 2013 壓力及效能工具的功能是產生虛設的設定檔的位置資訊服務。 位置資訊服務通常沒有任何明顯的效能影響的伺服器上。

![位置資訊服務設定] 索引標籤。](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "位置資訊服務設定] 索引標籤。")

如果您選擇來測試這項功能，您可以在表單中所述的值填滿，然後按一下 [產生 LIS 組態檔] 按鈕。 它將會產生 CSV 檔案稱為 LIS\_Subnet.csv，LIS\_Switches.csv、 LIS\_Ports.csv 和 LIS\_WAP.csv。 您可以再匯入這些 CSV 檔案 LIS 資料庫使用**組 CsLisSubnet**指令程式、**設定 CsLisSwitch**指令程式、**設定 CsLisPort** cmdlet 時及**組 CsWirelessAccessPoint** cmdlet 時，分別。

</div>

</div>

<span> </span>

</div>

</div>

</div>

