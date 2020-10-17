---
title: Lync Server 2013：將使用者移至企業語音
description: Lync Server 2013：將使用者移至 Enterprise Voice。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving users to Enterprise Voice
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412758(v=OCS.15)
ms:contentKeyID: 48184958
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41b075f916f4d81d8d3c24c24c7393be58e10a92
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542009"
---
# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a>在 Lync Server 2013 中將使用者移至企業語音

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

如果您要將使用者從現有的 PBX 電話語音基礎結構移至 Enterprise Voice，部署程式會包含一些步驟，這些步驟並非在 [Lync Server 2013 中規劃 Enterprise Voice](lync-server-2013-planning-for-enterprise-voice.md)時所述的規劃程式中的部分。 如需從舊版 Enterprise Voice 部署遷移使用者的詳細資訊，請參閱安裝媒體隨附的遷移檔。

將使用者從現有電話語音基礎結構移至 Enterprise Voice 的套裝程式含下列步驟：

1.  指定主要電話號碼。

2.  啟用使用者的企業語音。

3.  為使用者準備撥號對應表。

4.  規劃使用者語音原則。

5.  規劃通話路由。

6.  設定 PBX 或 SIP 主幹以為已啟用 Enterprise Voice 的使用者重新路由通話。

7.  將使用者移至 Exchange 整合通訊 (UM)  (建議) 。

本主題說明上述每個步驟所需的規劃。

<div>

## <a name="step-1-designate-primary-phone-numbers"></a>步驟 1： 指定主要電話號碼

Enterprise Voice 會與其他郵件媒體整合語音，如此一來，當來電到達伺服器時，伺服器會將該號碼對應至使用者的 SIP-URI，然後將該呼叫派生至與該 SIP-URI 相關聯的所有用戶端端點。 此程式需要每一位使用者都與主要電話號碼相關聯。

主要電話號碼必須：

  - 全域唯一或內部分機的情況，在企業中是唯一的。

  - 企業中的擁有和路由傳送。 不應該使用個人號碼。

企業使用者可在 Active Directory 網域服務中列出兩個以上的電話號碼。 在 [Active Directory 使用者及電腦] 嵌入式管理單元中，您可以在該使用者的屬性工作表上查看或變更所有與特定使用者相關聯的電話號碼。

[**使用者屬性**] 對話方塊的 [**一般**] 索引標籤上的 [**電話號碼**] 方塊應包含使用者的主要工作號碼。 此號碼通常會指定為使用者的主要電話號碼。

有些使用者可能會有特殊需求 (例如，想要讓所有來電都透過系統管理助理) 傳送，但例外狀況應只局限于需要明確且嚴重的情況。

選取主要號碼後，必須：

  - 盡可能正常化為 e.164 格式。

  - 複製到 Active Directory **msRTCSIP-line** 屬性。
    
    <div>
    

    > [!NOTE]  
    > <STRONG>與遠端呼叫控制共存 (RCC) </STRONG><BR>RCC 是使用 Lync Server 來監控及控制桌面 PBX 電話的功能。 控制是透過伺服器進行路由傳送，其充當 PBX 的閘道。 雖然您無法同時為 RCC 和 Enterprise Voice 設定使用者，但是行 URI 設定會指定使用者的主要電話號碼（以任一種情況為單位）。<BR>如果您有現有的 PBX 基礎結構，讓選取的使用者繼續使用，您可以將企業語音逐步引入您的組織。 如需此部署案例的詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-direct-sip-deployment-options.md">Lync Server 2013 中的直銷 SIP 部署選項</A> 。<BR>在舊版中，您可以為使用者同時啟用 RCC 和 Enterprise Voice，但只有在您也為雙重分叉設定使用者時，撥入電話會同時撥打使用者 PBX 電話和 Communicator 的功能。 在 Lync Server 2010 中，不支援雙重分叉。

    
    </div>

可用於填入 **msRTCSIP-line** 屬性的方法有三種：

  - 建議的 Microsoft Identity Integration Server () 

  - Lync Server 控制台中的 [ **使用者** ] 頁面

必須處理的電話號碼數目，組織所開發的腳本是比較好的選擇。 根據您的組織在 Active Directory 網域服務中表示電話號碼的方式，腳本可能必須先將主要電話號碼正常化為 e.164 格式，再將其複製到 **msRTCSIP-line** 屬性。

  - 如果您的組織在 Active Directory 網域服務中以單一格式維護所有的電話號碼，且該格式為 e.164，則您的腳本只需要將每個主要電話號碼寫入 **msRTCSIP-line** 屬性。

  - 如果您的組織在 Active Directory 網域服務中以單一格式維護所有的電話號碼，但該格式不是 e.164，您的腳本應定義適當的正規化規則，以便將主要電話號碼從現有的格式轉換為 e.164，然後再將主要電話號碼寫入 **msRTCSIP-line** 屬性。

  - 如果您的組織未在 Active Directory 網域服務中強制使用電話號碼的標準格式，則您的腳本應該定義適當的正規化規則，以便將主要電話號碼從其各種格式轉換為 e.164 相容性，然後再將主要電話號碼寫入 **msRTCSIP-line** 屬性。

您的腳本也必須先插入首碼 **電話：** 在每個主要號碼之前，再將它寫入 **msRTCSIP-line** 屬性。

此屬性中指定的數位預期格式為：

  - 電話： + 14255550100; ext = 50100。

  - 電話：針對獨特 enterprise wide 擴充的 5550100 () 
    
    <div>
    

    > [!IMPORTANT]  
    > 由 Address Book Service () ABS 所執行的正規化，不會取代或不再需要正常化 Active Directory 網域服務中每個使用者的主要電話號碼，因為 ABS 沒有 Active Directory 網域服務的存取權，因此無法將主要號碼複製到 <STRONG>msRTCSIP-line</STRONG> 屬性。

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a>步驟 2： 為使用者啟用企業語音

除了識別要啟用的使用者之外，不需要進行特殊規劃，即可完成此步驟。

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a>步驟 3： 為使用者準備撥號對應表。

已啟用 Enterprise Voice 的使用者將無法在未設定撥號對應表的情況下撥打 PSTN 電話。 撥號對應表是一個具名的正規化規則集，可將具名位置、個別使用者或連絡人物件的電話號碼轉譯成單一標準 (E.164) 格式，以便進行電話授權和電話路由傳送。 正規化規則會針對每個指定位置、使用者或連絡人物件，定義要如何路由傳送以各種格式表達的電話號碼。

如需有關準備撥號對應表的詳細資訊，請參閱 [Lync Server 2013 中的撥號對應表和正常化規則](lync-server-2013-dial-plans-and-normalization-rules.md)。

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a>步驟 4： 規劃使用者語音原則

在舊版 PBX 上的服務類別設定（例如從公司電話撥打長途電話或國際電話的權利）必須重新設定為 VoIP 原則，以供使用者移至 Enterprise Voice。 如需規劃及建立 Enterprise Voice 之原則的詳細資訊，請參閱 [Lync Server 2013 中的語音原則](lync-server-2013-voice-policies.md)。

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a>步驟 5： 規劃撥出電話路由

通話路由會指定 Lync Server 如何處理 Enterprise Voice 使用者撥出的電話。 當使用者撥打號碼時，如果有必要，伺服器會將撥號字串標準化為 e.164 格式，並嘗試將撥號字串與 SIP URI 相符。 如果伺服器無法進行相符，它會根據數目來套用傳出的呼叫路由邏輯。 定義該邏輯的最後一個步驟是針對每一組每個撥號對應表中所列的目的地電話號碼，建立個別的命名呼叫路由。

如需規劃通話路由的詳細資訊，請參閱 [Lync Server 2013 中的語音路由](lync-server-2013-voice-routes.md)。

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a>步驟 6： 設定 PBX 或 SIP 主幹以重新路由傳送 Enterprise Voice 使用者的通話

先前是裝載在傳統 PBX 上的使用者，或是在網際網路電話語音服務提供者的 SIP 主幹連線上， (ITSP) 會在移動之後保留其電話號碼。 唯一的需求是在移動之後，必須重新設定 PBX 或 SIP 主幹，才能將 Enterprise Voice 使用者的來電路由傳送至轉送伺服器。

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a>步驟7。 將使用者移至 Exchange 整合通訊 (建議) 

將使用者移至 Exchange 整合通訊包含下列工作：

  - 將 Exchange 整合通訊和 Lync 伺服器設定為一起運作。

  - 為使用者啟用 Exchange 整合通訊呼叫應答和 Outlook Voice Access。 這種工作是在 Exchange 整合通訊伺服器上執行。 如需詳細資訊，請參閱 Exchange Server 2010 TechNet 程式庫，網址為 [https://go.microsoft.com/fwlink/p/?linkID=139372](https://go.microsoft.com/fwlink/p/?linkid=139372) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

