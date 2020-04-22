---
title: Lync Server 2013： Lync Server 混合式環境的概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Lync Server 2013 hybrid environment
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204669(v=OCS.15)
ms:contentKeyID: 48183399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b39c94b08da65e546fdf3ad01d42ada636ff371d
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a>Lync Server 2013 混合式環境的概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-28_

Lync Server 2013 混合式環境指的是內部部署的 Lync Server 2013 和其他使用者（位於 Lync Online 中）中有一些使用者，但使用者共用相同的網域，例如 user@contoso.com。

<div>

## <a name="about-this-guide"></a>關於本指南

本指南說明設定 Lync Server 2013 環境與 Lync Online 互通性時所需的工作，然後將您的內部部署使用者移至使用 Lync Online。

</div>

<div>

## <a name="prerequisites"></a>必要條件

您必須安裝下列應用程式和公用程式，才可完成設定混合式部署的工作。 這些檔案的安裝程式會包含在您部署的安裝媒體上，以及下列清單中包含的連結。

  - [Active Directory Federation Services (AD FS) 2.0](https://go.microsoft.com/fwlink/p/?linkid=257305)

  - [Microsoft 目錄同步作業工具9。1](https://go.microsoft.com/fwlink/p/?linkid=257307)

  - [安裝 Windows PowerShell 以進行單一登入與 AD FS](https://go.microsoft.com/fwlink/p/?linkid=398710)

  - Microsoft Online Services 登入小幫手（msoidcli-7.0）隨附于 Office 365 的桌面設定，可從 Microsoft 365 系統管理中心連結的下載頁面獲得。

</div>

<div>

## <a name="administrator-credentials"></a>系統管理員認證

當系統要求您提供系統管理員認證時，請使用 Office 365 組織之系統管理員帳戶的使用者名稱和密碼。 當您設定 Active Directory Federation Services （AD FS）2.0、目錄同步處理、單一登入、同盟及移動使用者至 Lync Online 時，也會使用這些認證。

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a>連接至 Lync Online PowerShell

管理員現在具備使用 Windows PowerShell 管理 Lync Online 和其 Lync Online 使用者帳戶的能力。 若要這麼做，您必須先從 Microsoft 下載中心下載 Lync Online Connector 模組（https://go.microsoft.com/fwlink/?LinkId=294688)。 如需下載、安裝和使用 Lync Online 連接器模組的詳細資訊，以及使用 Windows PowerShell 來管理 Lync Online 的詳細資訊，請參閱[使用 windows PowerShell 管理 Lync online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

