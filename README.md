#pragma once

constexpr int MAX_NUM_OF_PLAYERS = 32;

class Vector3
{
public:
    float x, y, z;
};

class Entity
{
public:
    uint32_t m_vtable; //0x0000
    Vector3 m_head; //0x0004
    char pad_0010[36]; //0x0010
    Vector3 m_feet; //0x0034
    Vector3 m_view_angle; //0x0040
    char pad_004C[172]; //0x004C
    int32_t m_health; //0x00F8
    char pad_00FC[560]; //0x00FC
    int32_t m_team_id; //0x032C
}; //Size: 0x0330

class EntityList
{
public:
    char pad_0000[4]; //0x0
    Entity* m_entity_ptr[MAX_NUM_OF_PLAYERS - 1]; //0x4
};
