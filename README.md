# polyamory-event-people-choser

A simple simulation to test various algorithms for choosing people for poly events with limited
seats available.

## The problem

There are several polyamory meetups happening throughout the year. Due to the community steadily
rising, some events face the problem that more people want to attend as there are seats available.

In normal circumstances, people could be chosen at random from the list of applicants until all
seats are filled, which would be a totally fair way to do it.

However, the attendees are mostly polyamorous, a lot of them want to attend with their whole
polycule. Chosing individual people at random, would lead to polycules being split up, which needs
to be avoided.

There is no algorithm which can solve this problem perfectly [quod esset demonstrandum], but some
are more fair than others.

## The simulation

The purpose of this program is to simulate various scenarios and use different algorithms to choose
people for the events. The results can then be compared to see which algorithm is the most fair.

## Configuration

Create a copy of `config.json.example` and name it `config.json`.

This file contains the following sections:

### `polycule_datasets`

A list of different datasets for autogenrating sample polycules. Each dataset is a dictionary of
polycule sizes and the number of polycules of that size.

e.g.:

```json
{
  "polycule_datasets": [
    {
      "1": 10,
      "2": 5,
      "3": 2
    }
  ]
}
```

This would create 10 polycules of size 1, 5 polycules of size 2 and 2 polycules of size 3.

### `available_spots`

A simple list of numbers of spots available. For each entry all polycule_datasets will be simulated.

### `runs_per_set`

How oftem is each combination of polycule_dataset, available_spots, and algorithm run.

### `output_format`

Valid options are `json`, `yaml`, and `text` for human readable output.
