class Episode 
{
    constructor(title, duration, hasbeenWatched)
    {
        this.title=title;
        this.duration=duration;
        this.hasbeenWatched=hasbeenWatched;
    }

    display()
    {
        console.log("Titre du film : " + this.title + ". Durée du film : " + this.duration + ". A-t-il été vue ? : " + this.hasbeenWatched);
    }
}

let episode = [];

let firstEpisode = new Episode ("Le seigneur des anneaux", 200, true);
let secondEpisode = new Episode ("Star Wars", 150, false);
let thirdEpisode = new Episode ("Avengers", 120, true);

let Nom_film;

episode.push(firstEpisode);
episode.push(secondEpisode);
episode.push(thirdEpisode);
episode.pop();
episode.unshift(new Episode ("Friends", 20, true));

for (let i in episode)
{
    if(episode[i].hasbeenWatched)
        {episode[i].hasbeenWatched="Vue";}
    else
        {episode[i].hasbeenWatched="Pas vue";}

    while(episode[i].duration>180 || episode[i].duration<30)
    {
        if(episode[i].duration<30)
            {episode[i].duration++;}
        if(episode[i].duration>180)
            {episode[i].duration--;}
        
    }
    
    switch(episode[i].title)
    {
        case "Le seigneur des anneaux" :
            Nom_film="Film trouvé";
            break;
        case "Star Wars" :
            Nom_film="Film trouvé";
            break;
        default :
            Nom_film="Film non trouvé";
    }

    console.log("Film : " + episode[i].title + ", " + Nom_film);
}

for (episode of episode)
    console.log(episode.display());