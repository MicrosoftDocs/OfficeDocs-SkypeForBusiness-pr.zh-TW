---
title: Lync Server 2013：將使用者移至企業語音
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Moving users to Enterprise Voice
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412758(v=OCS.15)
ms:contentKeyID: 48184958
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1127bd0c767da7f02df8aefb30fda41a64bd353a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40973999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a>在 Lync Server 2013 中將使用者移至企業語音

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

如果您是將現有的 PBX 電話結構中的使用者移至企業語音，則部署程式會包含一些並非在[Lync Server 2013 規劃企業語音](lync-server-2013-planning-for-enterprise-voice.md)的規劃程式中所述的步驟。 如需從舊版企業語音部署中遷移使用者的相關資訊，請參閱安裝媒體隨附的 [遷移檔]。

將使用者從現有的電話架構移至企業語音的程式，包括下列步驟：

1.  指定主要電話號碼。

2.  允許使用者使用企業語音。

3.  為使用者準備撥號方案。

4.  規劃使用者語音原則。

5.  規劃通話路線。

6.  設定 PBX 或 SIP 幹線來重新路由針對企業語音啟用的使用者的通話。

7.  將使用者移至 Exchange 整合通訊（UM）（建議使用）。

本主題描述每個步驟所需的規劃。

<div>

## <a name="step-1-designate-primary-phone-numbers"></a>步驟1。 指定主要電話號碼

企業語音會將語音與其他訊息媒體整合，在來電到達伺服器時，伺服器會將號碼對應至使用者的 SIP URI，然後將呼叫派生到與該 SIP URI 相關的所有用戶端端點。 這個程式要求每個使用者都要與主要電話號碼相關聯。

主要電話號碼必須是：

  - 全域唯一或（如果是內部擴充），在企業中則是唯一的。

  - 在企業中擁有及路由。 不應使用個人號碼。

企業使用者可以在 Active Directory 網域服務中列出兩個或多個電話號碼。 在 Active Directory 使用者和電腦管理單元中，您可以在該使用者的屬性工作表上查看或變更所有與特定使用者相關聯的電話號碼。

[**使用者屬性**] 對話方塊的 [**一般**] 索引標籤上的 [**電話號碼**] 方塊中應包含使用者的主要公司電話號碼。 這個數位通常會指定為使用者的主要電話號碼。

有些使用者可能會有特殊需求（例如，想要讓所有來電都透過管理小幫手傳送），但這類例外狀況只會限制為需要清楚且不重要的那些例外狀況。

選取主要數位之後，必須：

  - 盡可能正常化為. 164 格式。

  - 已複製到 Active Directory **msRTCSIP line**屬性。
    
    <div>
    

    > [!NOTE]  
    > <STRONG>與遠端通話控制（RCC）共存</STRONG><BR>RCC 是使用 Lync Server 來監視及控制桌面 PBX 手機的功能。 控制是透過伺服器路由的，可充當 PBX 的閘道。 雖然您無法同時設定 RCC 和企業語音的使用者，但 [列 URI] 設定會在任何情況下指定使用者的主要電話號碼。<BR>如果您有您想要讓使用者繼續使用的現有 PBX 基礎結構，您可以將企業語音逐步引入您的組織。 如需此部署案例的詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-direct-sip-deployment-options.md">Lync Server 2013 中的直接 SIP 部署選項</A>。<BR>在前一個版本中，您可以為使用者啟用 RCC 和企業版語音，但只有當您同時設定雙重呼叫的使用者時，傳入通話會同時撥打使用者的 PBX 手機和 Communicator 的功能。 在 Lync Server 2010 中，不支援雙分叉。

    
    </div>

有三種方法可填充**msRTCSIP**屬性：

  - Microsoft 身分識別整合伺服器（建議使用）

  - Lync Server [控制台] 中的 [**使用者**] 頁面

在必須處理多個電話號碼的情況下，您組織所開發的腳本是比較好的選擇。 根據貴組織在 Active Directory 網域服務中代表電話號碼的方式，此腳本可能必須先將主要電話號碼標準化為 E. 164 格式，然後才能將其複製到**msRTCSIP**屬性。

  - 如果您的組織以單一格式維護 Active Directory 網域服務中的所有電話號碼，而如果該格式是 E. 164，您的腳本只需要將每個主要電話號碼寫入**msRTCSIP**屬性。

  - 如果您的組織以單一格式維護 Active Directory 網域服務中的所有電話號碼，但該格式不是 E. 164，您的腳本應該定義適當的正常化規則，以便將主要電話號碼從其現有的格式轉換為 E.i，然後再將其寫入**msRTCSIP**屬性。

  - 如果您的組織沒有在 Active Directory 網域服務中強制執行電話號碼的標準格式，您的腳本應該定義適當的正常化規則，將主要電話號碼從其各種格式轉換為 MsRTCSIP，然後再將主要電話號碼寫入**** 屬性。

您的腳本也必須插入前置詞**電話：** 在將主要號碼寫入**msRTCSIP**屬性之前。

這個屬性所指定之數位的預期格式為：

  - 電話： + 14255550100; ext = 50100。

  - 電話：5550100（適用于獨特的企業廣泛延伸）
    
    <div>
    

    > [!IMPORTANT]  
    > 通訊錄服務（ABS）執行的正常化不會取代，也不需要在 Active Directory 網域服務中將每個使用者的主要電話號碼標準化，因為 ABS 沒有 Active Directory 網域服務的存取權，因此無法將主要數位複製到<STRONG>msRTCSIP</STRONG>屬性。

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a>步驟2。 為使用者啟用企業語音

除了識別要啟用的使用者之外，不需要進行特殊規劃，就能完成這個步驟。

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a>步驟3。 為使用者準備撥號方案。

已啟用企業語音的使用者將無法呼叫 PSTN，而不需撥號方案。 撥號方案是一組命名的正常化規則，可將命名位置、個別使用者或連絡人物件的電話號碼轉換成單一標準（e. 164）格式，以用於手機授權及呼叫路由。 正常化規則定義以各種格式表示的電話號碼如何針對每一個指定的位置、使用者或連絡人物件進行路由。

如需有關準備撥號方案的詳細資訊，請參閱[Lync Server 2013 中的撥號方案和正常化規則](lync-server-2013-dial-plans-and-normalization-rules.md)。

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a>步驟4。 規劃使用者語音原則

在舊版 PBX （例如從公司手機撥打遠距離或國際電話）上的 [使用者類別] 設定，必須針對移至企業語音的使用者，將其重新配置為 VoIP 原則。 如需規劃及建立企業語音原則的詳細資料，請參閱[Lync Server 2013 中的語音原則](lync-server-2013-voice-policies.md)。

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a>步驟5。 規劃出站通話路線

[通話路線] 可指定 Lync Server 處理企業語音使用者所放的出站通話的方式。 當使用者撥打電話號碼時，如有必要，伺服器會將撥號字串標準化為 E.i 格式，並嘗試將它與 SIP URI 相符。 如果伺服器無法進行相符，就會根據數位來套用撥出電話路由邏輯。 定義該邏輯的最後一個步驟是為每一組在每個撥號計畫中列出的目的地電話號碼建立單獨的命名呼叫路線。

如需規劃通話路線的詳細資料，請參閱[Lync Server 2013 中的語音路由](lync-server-2013-voice-routes.md)。

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a>步驟6。 設定 PBX 或 SIP 幹線來重新路由企業語音使用者的通話

在傳統 PBX 或 SIP 中繼連線中，原有的使用者是以網際網路電話服務提供者（ITSP）為宿主，在移動之後，就會保留他們的電話號碼。 唯一的需求是，在移動之後，必須重新配置 PBX 或 SIP 幹線，才能將企業語音使用者的來電路由到中繼伺服器。

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a>步驟7。 將使用者移至 Exchange 整合訊息（建議使用）

將使用者移至 Exchange 整合訊息包含下列任務：

  - 設定 Exchange 整合訊息和 Lync 伺服器共同作業。

  - 允許使用者使用 Exchange 整合訊息呼叫應答及 Outlook 語音存取。 此工作是在 Exchange 整合通訊伺服器上執行。 如需詳細資訊，請參閱 Exchange Server 2010 TechNet [http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372)文件庫。

</div>

</div>

<span> </span>

</div>

</div>

</div>

