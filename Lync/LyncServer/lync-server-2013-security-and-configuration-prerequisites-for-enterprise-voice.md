---
title: Enterprise Voice 的安全性和組態先決條件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Security and configuration prerequisites for Enterprise Voice
ms:assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398221(v=OCS.15)
ms:contentKeyID: 48183495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d06cdb4c679d1a40eb5c6fa0e8cf837ec8d2e332
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 中的企業語音安全性與設定先決條件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

確認您的基礎結構符合下列安全性、使用者配置和案例特定的硬體先決條件。

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a>管理許可權與證書基礎結構

請確定您的環境已使用下列管理使用者群組和證書基礎結構加以設定，以便在企業語音部署程式中使用。

  - 部署企業語音的系統管理員應該是 RTCUniversalServerAdmins 群組的成員。

  - 執行設定任務的系統管理員必須具備足夠的許可權：
    
      - **CsVoiceAdministrator：** 這個系統管理員角色可以執行語音設定工作、管理語音應用程式，以及將語音原則指派給最終使用者。
    
      - **CsUserAdministrator：** 這個系統管理員角色可以管理使用者屬性，例如為使用者啟用企業語音。 除了封存原則之外，此管理員角色還可以指派每個使用者的原則;移動使用者;以及管理常見的區域電話和類比裝置。
    
      - **CsAdministrator：** 此系統管理員角色可以執行 CsVoiceAdministrator 和 CsUserAdministrator 的所有工作。
    
    <div>
    

    > [!NOTE]
    > 委派能讓更多的系統管理員參與您的 Lync Server 部署，而不需要開啟對資源的不必要存取權。

    
    </div>

  - 管理的金鑰結構（MKI）是透過 Microsoft 或協力廠商憑證授權單位（CA）基礎結構來部署和設定。
    
    <div>
    

    > [!NOTE]
    > 如需有關 Lync Server 中證書需求的詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-certificate-infrastructure-requirements.md">Lync Server 2013 證書基礎結構需求</A>。

    
    </div>

</div>

<div>

## <a name="user-configuration"></a>使用者設定

如果您在前端部署期間 collocated 每個前端池或標準版伺服器的中繼伺服器，則在安裝這些伺服器角色的檔案期間，系統會自動設定企業語音所需的使用者設定。

如果您目前正在新部署企業語音工作負載，請在開始進行部署程式之前，為您打算啟用企業語音的每位使用者指定主要電話號碼。 身為管理員，您必須負責確保此號碼是唯一的。 在實施前，所有的主要電話號碼都必須經過標準化（正確格式化），並使用 Lync Server [控制台] 複製到每個使用者的**行 URI**屬性。

<div>


> [!NOTE]
> 如需企業語音部署所需的主要電話號碼範例，請參閱規劃檔中的 lync server <A href="lync-server-2013-dial-plans-and-normalization-rules.md">2013</A>中的 [lync server 2013] 區段中的<A href="lync-server-2013-dial-plans-and-normalization-rules.md">撥號方案與正常化規則</A>。



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>後續步驟：安裝檔案或設定 PSTN 連線能力

在驗證企業語音的軟體與環境先決條件之後，您可以使用下列內容來執行下列其中一項操作：

  - 安裝中繼伺服器，如在[Lync server 2013 中安裝用於進行轉送服務伺服器](lync-server-2013-install-the-files-for-mediation-server.md)的檔案中所述，但僅限您想要部署獨立的中繼伺服器或池，因為在 collocated 時，會將轉送伺服器安裝為前端池或標準版伺服器部署程式的一部分。

  - 或者，開始設定設定以傳送企業語音使用者的呼叫，如在[Lync Server 2013 中設定 trunks 中](lync-server-2013-configuring-trunks.md)所述。

</div>

</div>

<span> </span>

</div>

</div>

</div>

