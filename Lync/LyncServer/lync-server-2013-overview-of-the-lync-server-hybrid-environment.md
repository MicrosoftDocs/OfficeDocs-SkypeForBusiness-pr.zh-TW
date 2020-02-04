---
title: Lync Server 2013：Lync Server 混合式環境概觀
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
ms.openlocfilehash: 0594ddc0433bdcc227c693c4842c08bf7d05989f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a>Lync Server 2013 混合式環境概觀

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-28_

Lync Server 2013 混合式環境指的是在內部部署 Lync Server 2013 和其他使用者駐留在 Lync Online 的使用者，但使用者共用同一個網域，例如 user@contoso.com。

<div>

## <a name="about-this-guide"></a>關於本指南

本指南說明設定您的 Lync Server 2013 環境以進行 Lync Online 互通性所需執行的工作，然後從內部部署的部署將使用者移至使用 Lync Online。

</div>

<div>

## <a name="prerequisites"></a>先決條件

您必須安裝下列應用程式和實用程式，才能完成設定混合式部署的工作。 這些檔案的安裝程式會包含在您的部署所提供的安裝媒體，以及下列清單中的連結。

  - [Active Directory 同盟服務（AD FS）2。0](http://go.microsoft.com/fwlink/p/?linkid=257305)

  - [Microsoft Directory 同步處理工具9。1](http://go.microsoft.com/fwlink/p/?linkid=257307)

  - [安裝 Windows PowerShell 以進行單一登入與 AD FS](http://go.microsoft.com/fwlink/p/?linkid=398710)

  - Microsoft Online Services 登入小幫手（msoidcli-7.0）隨附于 Office 365 的桌面設定，可從 Office 365 系統管理入口網站連結至的下載頁面中取得。

</div>

<div>

## <a name="administrator-credentials"></a>系統管理員認證

當系統詢問您是否要提供您的系統管理員認證時，請針對您的 Office 365 租使用者使用系統管理員帳戶的使用者名稱和密碼。 當您設定 Active Directory Federation Services （AD FS）2.0、目錄同步處理、單一登入、同盟，以及將使用者移至 Lync Online 時，您也會使用這些認證。

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a>連線至 Lync Online PowerShell

系統管理員現在能夠使用 Windows PowerShell 來管理 Lync Online 及其 Lync Online 使用者帳戶。 若要這樣做，您必須先從 Microsoft 下載中心下載並安裝 Lync Online 連接器模組（http://go.microsoft.com/fwlink/?LinkId=294688)。 如需有關下載、安裝及使用 Lync Online 連接器模組的詳細資訊，以及如何使用 Windows powershell 來管理 lync Online 的詳細資訊，請參閱[使用 Windows powershell 管理 lync](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)online。

</div>

</div>

<span> </span>

</div>

</div>

</div>

