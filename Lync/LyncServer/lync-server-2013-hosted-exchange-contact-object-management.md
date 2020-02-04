---
title: Lync Server 2013：主控 Exchange 聯絡人物件管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange Contact object management
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412978(v=OCS.15)
ms:contentKeyID: 48185748
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c63e9952abab192e7f8f4a71e97a660d2798d3b9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a>Lync Server 2013 中的主控 Exchange 聯絡人物件管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-25_

您必須針對跨平臺部署中的每個自動助理編號和訂閱者存取號碼設定連絡人物件。

若要與託管 Exchange UM 整合，ocsumutil 無法用來管理連絡人物件，因為它依賴 Active Directory Exchange UM 設定。 在跨內部部署中，Lync Server 2013 和託管 Exchange UM 會安裝在不同的林中，且不受信任。 出於安全考慮，Lync Server 2013 系統管理員無法直接存取 Exchange UM Active Directory 設定。 因此，Lync Server 2013 提供不同的模型，可在 Lync Server 2013 和託管 Exchange UM 服務的*共用 SIP 位址空間*中管理連絡人物件。

<div>

## <a name="hosted-contact-object-workflow"></a>託管連絡人物件工作流程

以下是使用託管 Exchange 租使用者系統管理員來管理連絡人物件的一般步驟：

1.  Exchange 管理員會要求 Exchange UM 訂閱者存取及自動助理連絡人物件的電話號碼。

2.  Lync Server 2013 系統管理員會針對每個電話號碼建立連絡人物件，並將託管的語音信箱原則指派給每一個連絡人物件。

3.  Lync Server 2013 系統管理員會將電話號碼提供給 Exchange 系統管理員。

4.  Exchange 管理員會將電話號碼指派給適當的 Exchange UM 撥號方案，以進行自動語音應答及訂閱者存取。

<div>


> [!NOTE]  
> 您不需要在連絡人物件上設定任何 Lync Server 2013 撥號方案設定，就像內部部署部署一樣。



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a>設定託管連絡人物件

<div>


> [!NOTE]  
> 在 Lync Server 2013 連絡人物件可供託管 Exchange UM 使用之前，必須先部署適用于它們的託管語音信箱原則。 原則可以是全域、網站層級或每使用者範圍，只要它套用至您要啟用的連絡人物件。 如需詳細資訊，請參閱<A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中託管的語音信箱原則</A>。



</div>

若要在跨內部部署中設定託管的自動助理及訂閱者存取連絡人物件，您必須使用下列 Cmdlet：

  - [**新-CsExUmContact** ] 會為 [託管 UM] 建立新的連絡人物件。

  - [**設定] CsExUmContact**會修改託管 Exchange UM 的現有連絡人物件。

下列範例會建立自動助理連絡人物件：

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

這個範例會使用 SIP 位址 sip:exumaa1@fabrikam.com 來建立新的 Exchange UM 連絡人物件。 Lync Server 2013 註冊機構服務正在執行的池名稱是 RedmondPool.litwareinc.com。 儲存此資訊的 Active Directory 組織單位為 OU = ExUmContacts、DC = litwareinc、DC = com。 連絡人物件的電話號碼是2065554567。 [選用自動調整] $True 參數會指定此物件是自動助理連絡人物件。 將-自動助理參數設定為 False （預設值），會指定訂閱者存取連絡人物件。

如需有關新的 CsExUmContact 和 CsExUmContact Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。

</div>

</div>

<span> </span>

</div>

</div>

</div>

