---
title: Lync Server 2013：語音原則
description: Lync Server 2013：語音原則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice policies
ms:assetid: b7433c62-9d8c-48af-89a0-19f0d34806ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412891(v=OCS.15)
ms:contentKeyID: 48185223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b85e69c83a8f964d9114a83abe6978f040f044d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549829"
---
# <a name="voice-policies-in-lync-server-2013"></a>Lync Server 2013 中的語音原則

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

Lync Server *語音原則* 針對指派原則的每個使用者、網站或組織，定義下列各項：

  - 一組可啟用或停用的呼叫功能，可決定使用者可使用的 Enterprise Voice 功能。

  - 一組公用交換電話網路 (PSTN) 使用方式記錄，可定義授權的來電類型。

<div>

## <a name="planning-for-voice-policies"></a>規劃語音原則

下列步驟可協助您規劃企業語音部署所需的語音原則：

  - 決定如何設定全域語音原則 (隨產品) 安裝的預設語音原則。 這個原則會套用至所有未明確指派網站層級或每位使用者原則的 Enterprise Voice 使用者。

  - 識別您可能需要的任何網站層級語音原則。

  - 識別您可能需要的任何個別使用者語音原則。

  - 決定要針對每個語音原則啟用哪些通話功能。

  - 決定要針對每個語音原則設定的 PSTN 使用方式記錄。

<div>

## <a name="voice-policy-scope"></a>語音原則範圍

*語音原則範圍* 決定原則可以套用的層級。 在 Lync Server 中，您可以設定具有下列範圍層級的語音原則， (依最常見的) 列出。

  - **使用者語音原則** 可以指派給個別的使用者、群組或連絡人物件。 這是最低的層級原則。 您可以部署使用者語音原則，以在網站上啟用特定使用者或群組的功能，而不是在相同網站中的其他使用者。 例如，您可能想要對某些員工停用長途撥號。 出於指派語音原則的目的，連絡人物件會被視為個別使用者。
    
    <div>
    

    > [!NOTE]  
    > 建議您部署使用者語音原則，以供向中央網站部署註冊的分支網站 Enterprise Voice 使用者或已在 Survivable Branch 裝置上登錄的使用者。

    
    </div>

  - **網站語音原則** 適用于整個網站，但不包括指派使用者語音原則的任何使用者、群組或連絡人物件。 若要定義網站語音原則，您必須指定要套用原則的網站。 若未指派使用者語音原則，則會使用網站語音原則。

  - **Global voice policy** 是隨產品一起安裝的預設語音原則。 您可以編輯全域語音原則，以符合組織的特定需求，但是您無法重新命名或刪除。 這個語音原則會套用至部署中的所有 Enterprise Voice 使用者、群組和連絡人物件，除非您設定並指派具有更特定範圍的語音原則。 若要完全停用這個原則，請確定所有的網站和使用者都有指派的自訂原則。

</div>

<div>

## <a name="call-features"></a>通話功能

您可以針對每個語音原則啟用或停用下列通話功能：

  - **[來電轉接]** 可讓使用者將來電轉接到其他電話和用戶端裝置。 預設為啟用。

  - **[委派]** 可讓使用者指定其他使用者，來代表他們撥號和接聽電話。 預設為啟用。

  - **[通話轉接]** 可讓使用者將通話轉接給其他使用者。 預設為啟用。

  - **通話駐留** 可讓使用者寄存通話，然後從不同的電話或用戶端挑選來電。 預設為停用。

  - **同時震鈴** 允許來電撥打額外的電話 (例如，行動電話) 或其他端點裝置。 預設為啟用。

  - **[小組通話]** 可讓所定義小組的使用者接聽該小組其他成員的通話。 預設為啟用。

  - **PSTN 重新路由** 功能可讓指派此原則的使用者所撥打的使用者，在公用交換電話網路 (PSTN) （WAN 遭到擁塞或無法使用時）進行重新路由傳送。 預設為啟用。

  - **頻寬原則覆寫** 可讓系統管理員覆寫特定使用者的通話許可控制原則決定。 預設為停用。

  - **惡意的呼叫追蹤功能** 可讓使用者使用 Lync 用戶端來報告惡意通話，然後在詳細通話記錄中旗標此通話。 預設為停用。

  - **語音信箱 escape** 可在設定同時震鈴時，立即將來電路由傳送到使用者的行動電話語音信箱系統，而且電話會關閉、電池計量不足或範圍外，而且會以計時器值為基礎。 這項設定可啟用及停用計時器，並設定計時器的值。 只能使用 Lync Server 管理命令介面來設定它。 預設為停用。

  - **來電轉接和同時響鈴 PSTN 使用** 方式可讓系統管理員指定與來電轉接和同時響鈴之語音原則相同的 PSTN 使用方式，將來電轉接和同時響鈴限制為僅限內部 Lync 使用者，或指定不同于語音原則 pstn 使用方式的自訂 PSTN 使用方式。 預設值是使用與來電轉接和同時響鈴的語音原則相同的 PSTN 使用方式。

</div>

<div>

## <a name="pstn-usage-records"></a>PSTN 使用方式記錄

每個語音原則都應有一或多個相關聯的 PSTN 使用方式記錄。 PSTN 使用方式可以與語音原則相關聯，以進行同時震鈴及來電轉接的目的。 如需規劃 PSTN 使用方式記錄的詳細資訊，請參閱 [Lync Server 2013 中的 PSTN 使用方式記錄](lync-server-2013-pstn-usage-records.md)。

<div>


> [!NOTE]  
> PSTN 使用順序很重要，因為在將使用者對應到路由時，輸出路由功能會比較 PSTN 使用方式，從上到下。 如果第一個使用方式符合通話路由，則會使用該路由。 否則，輸出路由功能會查看清單中的下一個 PSTN 使用狀況，並繼續直到找到相符專案為止。 實際上，如果清單中的第一個無法使用，後續的 PSTN 使用方式也會提供備份。



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

