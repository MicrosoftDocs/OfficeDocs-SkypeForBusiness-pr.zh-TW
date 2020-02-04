---
title: Lync Server 2013：配置支援的用戶端版本
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
ms.openlocfilehash: 9a262cab2145013d83cdae573d98b5db17e0e890
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-supported-client-versions-in-lync-server-2013"></a>在 Lync Server 2013 中設定支援的用戶端版本

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-12-14_

在 Lync Server 2013 中，您可以設定用戶端版本原則，以指定您的環境支援的用戶端版本。 此外，您也可以使用全域用戶端版本設定，為尚未定義版本原則的用戶端指定預設動作，因此，不是明確支援或受限制。

您也可以使用用戶端版本原則來管理用戶端更新。 當您設定用戶端版本原則並使用選項 [**允許**] 和 [升級及**封鎖及升級**] 時，用戶端將會從 Windows Server Update services 接收更新的軟體（如果您使用的是此服務）或 [Microsoft Update]。

<div>

## <a name="client-version-policy-settings"></a>用戶端版本原則設定

預設用戶端版本原則要求所有用戶端都執行 Lync。 如果您環境中的用戶端執行舊版的 Communicator，您可能需要重新設定用戶端版本規則，以免在連線至 Lync Server 2013 時，意外地封鎖或更新用戶端裝置。 您可以修改預設規則，或者您可以在用戶端版本原則清單中新增較高的規則，以覆寫預設規則。 此外，隨著累加更新（CUs）的發行，您應該將用戶端版本原則設定為需要最新的更新。 如需詳細資訊，請參閱在作業檔中[指定可用於登入 Lync Server 2013 的用戶端應用程式](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

