# Project-Clash
Data Analysis of Clash Royale API using Python

Getting opponent deck during loss..

battles_1v1_loss = []
for b in battles:
    if b.get('type') == 'PvP' and b.get('winner') < 0:
            battles_1v1_loss.append(b)
len(battles_1v1_loss)

opp_deck = []
for loss in battles_1v1_loss:
    opp_deck.append(loss.get('opponent')[0].get('deck'))

opp_cards = []
for deck in opp_deck:
    for cards in deck:
        opp_cards.append(cards.get('key'))

count = Counter(opp_cards).most_common()
