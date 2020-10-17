---
title: Lync Server 2013：設定支援的用戶端版本
description: Lync Server 2013：設定支援的用戶端版本。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring supported client versions
ms:assetid: aebf7b48-9aa2-4a06-adc5-0c9d11b6358d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412832(v=OCS.15)
ms:contentKeyID: 48185137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74396314cae864fae134531b71375c750be8d3da
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556879"
---
# <a name="configuring-supported-client-versions-in-lync-server-2013"></a>在 Lync Server 2013 中設定支援的用戶端版本

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-12-14_

在 [Lync Server 2013] 中，您可以設定用戶端版本原則，以指定環境中支援的用戶端版本。 此外，您可以使用全域用戶端版本設定，為尚未定義版本原則的用戶端指定預設動作，因此不會明確支援或限制此用戶端。

您也可以使用用戶端版本原則來管理用戶端更新。 當您設定用戶端版本原則，並使用「 **允許** 」和「升級」及「封鎖」及「 **升級**」的選項時，如果您使用此服務) 或 Microsoft Update，用戶端將會從 Windows Server Update Service 接收更新的軟體 (。

<div>

## <a name="client-version-policy-settings"></a>用戶端版本原則設定

預設用戶端版本原則要求所有用戶端都執行 Lync。 如果環境中的用戶端執行舊版的 Communicator，您可能需要重新設定用戶端版本規則，以避免在連線至 Lync Server 2013 時，意外封鎖或更新用戶端和裝置。 您可以修改預設規則，也可以新增高於用戶端版本原則清單中的規則，以覆寫預設規則。 此外，在發行 Cu)  (累計更新時，您應該將用戶端版本原則設定為要求最新的更新。 如需詳細資訊，請參閱操作檔中的 [指定可用於登入 Lync Server 2013 的用戶端應用程式](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

