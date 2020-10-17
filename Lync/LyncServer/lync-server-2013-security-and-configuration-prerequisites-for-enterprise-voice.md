---
title: Enterprise Voice 的安全性和設定必要條件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security and configuration prerequisites for Enterprise Voice
ms:assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398221(v=OCS.15)
ms:contentKeyID: 48183495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa8f0f3dd113b10a01f18a0542561de946d4acd0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510470"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 中的 Enterprise Voice 安全性和設定先決條件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

請確認您的基礎結構符合下列安全性、使用者設定和特定案例的硬體先決條件。

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a>系統管理權限和憑證基礎結構

請確認在 Enterprise Voice 部署過程中，您的環境是設定為下列系統管理使用者群組以及憑證基礎結構。

  - 部署 Enterprise Voice 的系統管理員應該是 RTCUniversalServerAdmins 群組的成員。

  - 執行設定工作的系統管理員必須具備適當的權限：
    
      - **CsVoiceAdministrator：** 此系統管理員角色可以執行語音設定工作、管理語音應用程式，以及指派語音原則給一般使用者。
    
      - **CsUserAdministrator：** 此系統管理員角色可以管理使用者屬性，例如啟用使用者的 Enterprise Voice。此系統管理員角色也可以指派個別使用者原則，封存原則除外；移動使用者；管理公用區電話和類比裝置。
    
      - **CsAdministrator：** 此系統管理員角色可以執行 CsVoiceAdministrator 和 CsUserAdministrator 的所有工作。
    
    <div>
    

    > [!NOTE]
    > 委派可讓更多系統管理員參與您的 Lync Server 部署，但不會開啟對資源的不必要存取。

    
    </div>

  - 已經使用 Microsoft 或協力廠商憑證授權單位 (CA) 的基礎結構，完成 Managed 金鑰基礎結構 (MKI) 的部署和設定。
    
    <div>
    

    > [!NOTE]
    > 如需 Lync Server 中憑證需求的詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-certificate-infrastructure-requirements.md">Lync Server 2013 的憑證基礎結構需求</A> 。

    
    </div>

</div>

<div>

## <a name="user-configuration"></a>使用者設定

如果您組合轉送伺服器與每個前端集區或 Standard Edition Server 的前端部署期間，則在安裝這些伺服器角色的檔案時，會自動設定企業語音所需的使用者設定。

如果您此時是全新部署 Enterprise Voice 工作量，在開始部署程序前，請先為每個您計畫要啟用 Enterprise Voice 的使用者指定主要電話號碼。 身為系統管理員，您要負責確認這個號碼是唯一的。 在執行之前，所有的主要電話號碼都必須正規化 (正確格式化) ，並使用 Lync Server 控制台將其複製到每個使用者的 **行 URI** 屬性。

<div>


> [!NOTE]
> 如需 Enterprise Voice deployment 所需的主要電話號碼範例，請參閱規劃檔中的 lync <A href="lync-server-2013-dial-plans-and-normalization-rules.md">2013 server</A> 2013 中的撥號對應表<A href="lync-server-2013-dial-plans-and-normalization-rules.md">和正常化規則</A>一節中的撥號對應表和正規化規則。



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>後續步驟：安裝檔案或設定 PSTN 連線

確定 Enterprise Voice 的軟體和環境先決條件後，可以遵循下列內容進行：

  - 如在 [Lync server 2013 中安裝轉送伺服器](lync-server-2013-install-the-files-for-mediation-server.md)的檔案所述，安裝轉送伺服器，但只有在您想要部署獨立轉送伺服器或集區時，因為在組合時已將轉送伺服器安裝為前端集區或 Standard Edition Server 部署程式的一部分。

  - 或者，開始設定設定以路由傳送 Enterprise Voice 使用者的通話，如在 [Lync Server 2013 中設定主幹中](lync-server-2013-configuring-trunks.md)所述。

</div>

</div>

<span> </span>

</div>

</div>

</div>

